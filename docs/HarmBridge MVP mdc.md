# HarmBridge: plano do MVP

## Hipótese

O MVP testa uma frase: pessoas com deficiência vão usar o HarmBridge para encontrar vagas inclusivas num só lugar, e empresas vão publicar vagas com informações claras de acessibilidade.

Se nenhum dos dois lados agir (candidatos clicando em vagas, empresas publicando), a hipótese cai e o produto muda antes de ganhar novas seções.

## Problema e usuários

O usuário principal ainda precisa ser escolhido: quem procura vaga ou quem contrata. A decisão define o que entra primeiro no backend.

| Usuário               | Dor provável                                                   | O que o MVP entrega                                            |
|-----------------------|----------------------------------------------------------------|----------------------------------------------------------------|
| Pessoa buscando vaga  | Vagas afirmativas espalhadas em sites de empresas diferentes   | Lista única com busca e filtros de cidade e modelo de trabalho |
| Empresa ou recrutador | Dificuldade de divulgar vagas afirmativas para o público certo | Formulário para publicar vaga com recursos de acessibilidade   |
| Equipe HarmBridge     | Não saber se alguém usa o site                                 | Painel com visitas, cliques, vagas publicadas e mensagens      |

As dores acima são hipóteses a confirmar nas conversas de validação, não fatos medidos.

## Escopo

O MVP mantém uma função central, as vagas inclusivas, e corta o que não ajuda a validar a hipótese.

| Entra no MVP                                          | Fica de fora por enquanto     |
|-------------------------------------------------------|-------------------------------|
| Lista de vagas com busca e filtros                    | Histórias reais               |
| Publicação de vaga por empresas                       | Locais acessíveis e mapa      |
| Formulário de feedback                                | Seção de impacto e avanços    |
| Painel de métricas e exportação                       | Login e cadastro de usuários  |
| Leitura em voz, fonte maior, alto contraste e VLibras | Moderação automática de vagas |

As seções que saem podem voltar depois, se a validação mostrar que o público as quer.

## Funcionalidades do MVP

O protótipo é um arquivo único, harmbridge-mvp.html, com seis funções.

| Função           | O que faz                                                                                         | Para quem |
|------------------|---------------------------------------------------------------------------------------------------|-----------|
| Lista de vagas   | Mostra 3 vagas oficiais (Localiza, Suzano, L'Occitane) e as publicadas pela comunidade            | Candidato |
| Busca e filtros  | Texto livre, cidade e modelo de trabalho, com contagem de resultados anunciada a leitores de tela | Candidato |
| Publicar vaga    | Formulário com empresa, cargo, cidade, modelo, link e recursos de acessibilidade; valida o link   | Empresa   |
| Feedback         | Nome, e-mail, perfil e mensagem                                                                   | Todos     |
| Painel da equipe | Visitas, cliques em "Ver vaga", vagas publicadas e mensagens                                      | Equipe    |

Vagas publicadas pela comunidade levam o selo "Publicada pela comunidade"; as oficiais levam "Fonte oficial".

## Acessibilidade

Os quatro recursos que você confirmou funcionando continuam no MVP: leitura em voz, fonte maior, alto contraste e VLibras. O que falta é testá-los com quem os usa de verdade.

- **Leitura em voz:** lê só o conteúdo principal, em blocos curtos, e tem botão de parar.

- **Fonte maior e alto contraste:** botões com estado anunciado (aria-pressed); a escolha fica salva entre visitas.

- **VLibras:** widget oficial carregado e inicializado na página.

Teste obrigatório antes de divulgar: ao menos uma pessoa usando leitor de tela (NVDA ou VoiceOver) e uma usando só teclado, percorrendo busca, candidatura e publicação de vaga.

## Arquitetura e backend

Hoje os dados ficam no localStorage, ou seja, só no navegador de quem usou: uma empresa publica uma vaga e ninguém mais a vê. Isso basta para demonstrar o fluxo, mas não para validar a hipótese com público real.

Todo acesso a dados passa pelo objeto store no código. Trocar o armazenamento significa reescrever só essas duas funções (get e set).

|                          | Agora (protótipo)                 | Próxima fase                                              |
|--------------------------|-----------------------------------|-----------------------------------------------------------|
| Onde ficam os dados      | localStorage do navegador         | Banco compartilhado (Supabase, Firebase ou Google Sheets) |
| Quem vê vagas publicadas | Só quem publicou                  | Todos os visitantes                                       |
| Quem lê as mensagens     | Ninguém além do próprio navegador | A equipe, em um painel                                    |
| Custo                    | Zero                              | Plano gratuito basta para começar                         |
| Moderação                | Nenhuma                           | Aprovar vaga antes de aparecer                            |

Decisão em aberto: qual serviço usar. Google Sheets é o mais simples de ler pela equipe; Supabase dá mais controle quando houver login.

## Plano de validação

A validação leva cerca de duas semanas e só começa depois que o backend compartilhado estiver ligado.

1.  Ligar o banco compartilhado e publicar o site em um endereço público.

2.  Convidar de 5 a 10 pessoas do público real, com ao menos uma usando leitor de tela.

3.  Pedir tarefas concretas: achar uma vaga em São Paulo, abrir a candidatura, mudar fonte e contraste, ouvir a página.

4.  Convidar 2 a 3 empresas ou recrutadores para publicar uma vaga de verdade.

5.  Anotar onde cada pessoa travou, sem ajudar, e ler as mensagens do formulário.

6.  Comparar os números do painel com as metas e decidir: continuar, ajustar ou mudar o foco.

## Métricas de sucesso

O MVP funciona se as duas pontas agirem. As metas abaixo são sugestões para a primeira rodada; ajuste conforme o tamanho do seu grupo de teste.

| Métrica                               | Onde medir        | Meta sugerida  |
|---------------------------------------|-------------------|----------------|
| Visitas únicas                        | Painel do MVP     | 50             |
| Cliques em "Ver vaga"                 | Painel do MVP     | 20             |
| Vagas publicadas por empresas         | Painel do MVP     | 3              |
| Mensagens de feedback                 | Painel do MVP     | 10             |
| Tarefas concluídas sem ajuda no teste | Observação direta | 4 de 5 pessoas |

O painel atual conta visitas por sessão do navegador. Para visitas únicas de verdade, o backend compartilhado precisa registrar um identificador anônimo.

## Riscos e limitações

O maior risco é divulgar o site com dados que só existem no navegador de cada pessoa.

| Risco                                                    | Efeito                                | Resposta                                                                                              |
|----------------------------------------------------------|---------------------------------------|-------------------------------------------------------------------------------------------------------|
| Dados em localStorage                                    | Vagas e mensagens não chegam à equipe | Ligar banco compartilhado antes de convidar testadores                                                |
| Vaga falsa ou desatualizada                              | Candidato perde tempo e confiança     | Selo "Publicada pela comunidade", aviso para confirmar no site da empresa e moderação na próxima fase |
| Dados pessoais no feedback                               | Nome e e-mail ficam armazenados       | Informar o uso dos dados e definir a política antes de lançar (LGPD)                                  |
| Recursos de acessibilidade só testados por quem os criou | Barreiras não vistas                  | Teste com usuários de leitor de tela e de teclado                                                     |
| Link de vaga que muda ou sai do ar                       | Cliques sem destino                   | Revisar as vagas oficiais a cada semana                                                               |
