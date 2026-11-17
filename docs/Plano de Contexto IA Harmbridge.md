# Plano de contexto para uso de IA – Harmbridge

Documento para ser colado no início de uma conversa com a IA (ou salvo como arquivo de contexto do projeto). Baseado no Diário de Bordo do Harmbridge.

## 1. Objetivo

Dar à IA o contexto mínimo para ajudar a desenvolver o site Harmbridge sem mudar o que já está pronto, sem inventar requisitos e sem repetir perguntas já respondidas.

## 2. Contexto do projeto

- **Projeto:** Harmbridge.
- **O que é:** site que conecta pessoas com deficiência a oportunidades de emprego, lazer e informações, de forma inclusiva.
- **Problema:** pessoas com dificuldades no acesso à internet.
- **Público-alvo:** moradores de São Paulo, escolas e empresas, com prioridade para pessoas com deficiência (PCD).
- **Objetivos:** informar sobre vagas de emprego e oportunidades de lazer, e evidenciar a importância do tema.
- **Ponto de partida:** já existia um projeto (uma home com todas as abas). A tarefa é adaptá-lo ao tema Harmbridge, mantendo a estrutura e trocando conteúdo e identidade.

## 3. Restrições (não negociáveis)

- Alterar **apenas a fonte dos títulos**; o restante do visual permanece.
- **Não alterar o tradutor de Libras**; ele acompanha o usuário em todas as seções.
- Site **responsivo** (celular, tablet e computador).
- O **mapa fica no fim da página**.
- A logo vai no cabeçalho, sem mexer no resto do layout.
- Aparência profissional, mantendo a estrutura existente.

## 4. Seções do site

| # | Seção | O que deve ter |
|---|-------|----------------|
| 1 | Histórias reais | Três histórias, cada uma com capa, link e breve resumo |
| 2 | Impacto | Benefícios da acessibilidade; incentivo a superar adversidades |
| 3 | Acessibilidade | **Foco a definir** (no original repetia o texto de Impacto) |
| 4 | Avanços | Avanços da acessibilidade que mais geraram valor para a sociedade |
| 5 | Locais | Lazer e entretenimento com acessibilidade e conforto |
| 6 | Vagas | Abas com nome, cargo, local e contato; usuários logados também publicam |
| 7 | Inclusão | Ajuste de tamanho da fonte e troca de cor |
| 8 | Guia | Formulário de opinião enviado à equipe (armazenado em Local Storage) |

**Resultado esperado:** site completo, funcional e responsivo, com todas as seções e o mapa ao final.

## 5. Como a IA deve trabalhar

- Fazer **uma etapa por vez** e esperar a validação antes de seguir.
- **Manter o que já funciona**; mudar só o que o pedido cita.
- Ao terminar, listar o que foi alterado e **como conferir** (arquivo, caminho, endereço local).
- Seguir as regras da pasta `docs` (HTML semântico, CSS, acessibilidade) e o README.
- Não criar funcionalidades extras, como upload de imagem, quando o grupo já definiu outra solução.

## 6. Como escrever bons prompts

Padrão que o diário mostra funcionando (versões "melhoradas" dos prompts 9 a 14):

1. Começar confirmando o estado: "A etapa anterior está correta."
2. Listar os pontos a validar de forma numerada.
3. Dizer o resultado esperado de cada ponto (por exemplo, "o formulário deve enviar e armazenar em Local Storage").
4. Relatar erros com o sintoma exato (mensagem, o que aparece e o que deveria aparecer).

**Exemplo:**

> A etapa anterior está correta. Agora preciso validar três pontos:
> 1. Fotos nas capas das notícias de inspiração.
> 2. Aba de vagas: publicar e listar.
> 3. Aba de opinião: o formulário deve enviar e armazenar em Local Storage.

## 7. Regras de documentação do projeto

Cada arquivo de regras fica na pasta `docs` e segue esta estrutura, com seis seções nesta ordem:

1. Objetivo
2. Contexto
3. Regras em tópicos
4. Exemplo concreto
5. Erros a evitar
6. Quando perguntar

**Padrões gerais:**

- Uma preocupação por arquivo, com menos de 80 linhas.
- Exemplos tirados do próprio repositório.
- Visão geral apontando para o README.
- Regras organizadas por escopo.
- Regra de acessibilidade.
- Commits pontuais.

**Arquivos previstos:** regras de HTML semântico e de CSS (refeitas no estilo Harmbridge) e atualização do README.

## 8. Erros a evitar (já ocorreram)

- **Logo não aparece:** conferir se o arquivo está na pasta do projeto e se o caminho no código está correto.
- **"Conexão recusada" no navegador:** verificar se o servidor local está em execução e informar endereço e porta corretos.
- **Imagens das capas:** as imagens ficam na pasta do projeto; a IA deve localizá-las e posicioná-las na capa correspondente, sem criar upload.
- **Aba de vagas e formulário de opinião:** não presumir que funcionam; testar publicar, listar e salvar.

## 9. Quando a IA deve perguntar

- O pedido toca em algo da lista de restrições (fonte, Libras, mapa, layout).
- Falta o foco da seção **Acessibilidade**.
- Um arquivo, caminho ou imagem citado não existe na pasta do projeto.
- A mudança exigiria alterar algo que já está pronto e validado.

## 10. Pendências em aberto

- [ ] Definir o foco da seção Acessibilidade.
- [ ] Validar a aba de vagas com vagas reais.
- [ ] Validar o armazenamento do formulário de opinião.
- [ ] Concluir as regras de HTML e atualizar o README.

## 11. Checklist antes de aceitar uma resposta da IA

- [ ] Só mudou o que foi pedido.
- [ ] Libras e mapa continuam como estavam.
- [ ] Funciona em celular, tablet e computador.
- [ ] Segue as regras da pasta `docs`.
- [ ] Foi testado no navegador, não só lido no código.
