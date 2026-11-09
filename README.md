# U-UNICID-ADS-CC-ENG-FRONTEND-2260030-N8-2-2026-NT-HarmBridge
Código fonte do projeto de site Unicid
HarmBridge
Site demonstrativo, em português do Brasil, sobre acessibilidade e inclusão de pessoas com deficiência. O projeto informa, dá visibilidade a histórias, reúne oportunidades e promove autonomia e participação social.

Visão do projeto

Problema: pessoas com deficiência enfrentam barreiras para acessar informação, oportunidades de trabalho e recursos que apoiem sua participação plena. A divulgação limitada também dificulta que empresas e iniciativas inclusivas alcancem esse público.
Público: pessoas com deficiência, familiares e cuidadores, empresas, organizações e pessoas interessadas em acessibilidade e diversidade. Priorize conteúdo e interação acessíveis a pessoas com deficiência.
Objetivos: informar sobre acessibilidade e inclusão; divulgar oportunidades e locais acessíveis; compartilhar histórias e avanços; conectar pessoas a recursos que apoiem autonomia e participação.
Stack e arquivos

HTML5, CSS3 e JavaScript nativos, sem frameworks.
site.rev01.html é a única página e contém o HTML, o CSS em <style> e o JavaScript em <script>.
docs/harmbridge-logo.png é o logotipo.
docs/foto-daniel-dias.jpg, docs/foto-terezinha-guilhermina.jpg e docs/foto-lais-souza.jpg são fotos das histórias.
Google Maps e VLibras são serviços externos e precisam de internet.
Não há public/, index.html, CSS separado, backend ou sistema de autenticação.
Página e seções

site.rev01.html contém, nesta ordem: início, histórias reais, impacto, acessibilidade, avanços, locais, vagas, inclusão, guia/contato e mapa. O mapa fica no final do conteúdo principal.

Funcionalidades e limites

Controles de fonte e tema guardam preferências no navegador.
A publicação de vagas usa armazenamento local de sessão e login demonstrativo; não publica nem autentica usuários em um servidor.
O formulário de opinião abre um rascunho endereçado a harmbridge@gmail.com; o visitante precisa enviar pelo aplicativo de e-mail.
Anúncios de emprego são externos e podem expirar. Confirmar detalhes no anúncio original.
Regras de desenvolvimento

Todos os arquivos de regras ficam em docs/ e usam .mdc: projeto-harmbridge.mdc, cursor-rules.mdc, self-improvement.mdc, html5.mdc, css3.mdc, javascript.mdc, acessibilidade.mdc e commits.mdc.

As regras em docs/ são documentação do projeto; não são carregadas automaticamente pelo Cursor ou pelo VS Code. Consulte-as ou anexe-as manualmente ao trabalhar em tarefas relacionadas. Mantenha cada arquivo abaixo de 80 linhas, com uma preocupação, frontmatter e as seis seções definidas em cursor-rules.mdc. Leia projeto-harmbridge.mdc antes de alterar estrutura, conteúdo ou funcionalidades.