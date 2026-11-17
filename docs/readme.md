# HarmBridge

**Conexões que transformam.** Site demonstrativo, em português do Brasil, sobre acessibilidade e inclusão de pessoas com deficiência. O projeto informa, dá visibilidade a histórias reais, reúne oportunidades e promove autonomia e participação social.

Código fonte do projeto de site Unicid (U-UNICID-ADS-CC-ENG-FRONTEND-2260030-N8-2-2026-NT-HarmBridge).

## Visão do projeto

- **Problema:** pessoas com deficiência enfrentam barreiras para acessar informação, oportunidades de trabalho e recursos que apoiem sua participação plena. A divulgação limitada também dificulta que empresas e iniciativas inclusivas alcancem esse público.
- **Objetivos:** informar sobre acessibilidade e inclusão; divulgar oportunidades e locais acessíveis; compartilhar histórias e avanços; conectar pessoas a recursos que apoiem autonomia e participação.

## Área de atuação

O HarmBridge atua na área de **acessibilidade e inclusão de pessoas com deficiência**, em quatro frentes:

| Frente | O que o projeto faz |
|--------|---------------------|
| Informação e conscientização | Reúne histórias reais, impacto e avanços da acessibilidade |
| Trabalho e emprego | Divulga vagas afirmativas para PCD e permite publicar vagas |
| Lazer e cultura | Indica locais com recursos de acessibilidade e mostra o mapa de São Paulo |
| Tecnologia assistiva | Oferece leitura em voz alta, Libras, ajuste de fonte e alto contraste |

**Abrangência:** informação e vagas em todo o Brasil, com foco em locais e mapa na cidade de São Paulo.

## Público-alvo

O público prioritário são **pessoas com deficiência (PCD)**, em especial moradores de São Paulo. O conteúdo e a interação devem ser acessíveis a elas em primeiro lugar.

| Público | Papel | O que encontra no site |
|---------|-------|------------------------|
| Pessoas com deficiência (prioridade) | Principal | Histórias reais, vagas inclusivas, locais acessíveis, recursos de leitura e acessibilidade |
| Familiares e cuidadores | Apoio | Informações sobre acessibilidade, locais com recursos e referências para acompanhar quem cuidam |
| Escolas | Educação | Histórias, impacto e avanços da acessibilidade para usar em atividades de conscientização |
| Empresas e organizações | Oportunidade | Vagas afirmativas para PCD e a opção de publicar vagas |
| Pessoas interessadas em acessibilidade e diversidade | Informação | Impacto, avanços e o guia de melhorias para enviar opinião |

## Stack e arquivos

- HTML5, CSS3 e JavaScript nativos, sem frameworks.
- `index.html` é a única página e contém o HTML, o CSS em `<style>` e o JavaScript em `<script>`.
- `docs/harmbridge-logo.png` é o logotipo.
- As imagens das histórias reais vêm das reportagens e páginas citadas em cada história.
- OpenStreetMap (mapa) e VLibras (tradutor de Libras) são serviços externos e precisam de internet.
- Não há pasta `public/`, CSS separado, backend ou sistema de autenticação.

## Página e seções

O `index.html` contém, nesta ordem, com navegação no cabeçalho:

| Seção | Conteúdo |
|-------|----------|
| Início | Apresentação do projeto e botão "Conheça nosso impacto" |
| Histórias reais | Três trajetórias brasileiras, cada uma com foto, resumo e link para a fonte (Régis Negro, Sonny Pólito e Glenda Felippe) |
| Impacto | Benefícios da acessibilidade: mais autonomia, conexão e futuro |
| Acessibilidade | Comunicação clara, espaços acolhedores e oportunidades reais |
| Avanços | Tecnologia assistiva, desenho universal e mercado diverso |
| Locais | Instituições com recursos de acessibilidade (Pinacoteca de São Paulo, MASP e Pina Contemporânea), com links para as páginas oficiais |
| Vagas | Vagas afirmativas reais com filtros (Todas, Todo o Brasil, São Paulo) e opção "Publicar vaga" |
| Inclusão | Opções de acessibilidade: tamanho da fonte, alto contraste e restaurar padrão |
| Guia | Formulário de opinião (nome, e-mail e opinião) enviado à equipe |
| Mapa | Mapa de São Paulo no final do conteúdo principal |

## Recursos de acessibilidade

- Botão **Ouvir esta página** (e **Parar leitura**) para leitura em voz alta.
- Tradutor de Libras (VLibras) disponível ao longo da página.
- Controle de tamanho da fonte (padrão e grande) e modo de alto contraste.
- Layout responsivo para celular, tablet e computador.

## Paleta de cores

| Uso | Cor | Código |
|-----|-----|--------|
| Cabeçalho e início do degradê da seção inicial | Azul-marinho | `#0B1F3A` |
| Degradê da seção inicial (tons seguintes) | Azul escuro e azul-petróleo | `#0F3361` e `#106884` |
| Botões e links de fonte | Azul de ação | `#1F5EFF` |
| Destaque, foco do teclado e chamada da seção inicial | Turquesa | `#18C7C0` |
| Fundo da página | Azul muito claro | `#F7FAFF` e `#E8F0F8` |
| Cartões e campos | Branco | `#FFFFFF` |
| Títulos | Azul-marinho escuro | `#15243B` |
| Texto corrido | Azul-acinzentado | `#40536B` |
| Texto sobre fundo escuro | Branco | `#FFFFFF` |

Valores medidos em capturas de tela do site publicado.

## Funcionalidades e limites

- Os controles de fonte e tema guardam preferências no navegador.
- A publicação de vagas usa armazenamento local de sessão e login demonstrativo; não publica nem autentica usuários em um servidor.
- O formulário de opinião armazena o conteúdo enviado em local storage do navegador.
- Anúncios de emprego e links de locais são externos e podem expirar ou mudar. Confirmar detalhes no anúncio ou na página oficial.

## Regras de desenvolvimento

Todos os arquivos de regras ficam na pasta `rules`, dentro da pasta `.cursor` (`.cursor/rules/`), e usam `.mdc`: `projeto-harmbridge.mdc`, `cursor-rules.mdc`, `self-improvement.mdc`, `html5.mdc`, `css3.mdc`, `javascript.mdc`, `acessibilidade.mdc` e `commits.mdc`.

---

**Site publicado:** https://harmbridgein.vercel.app
