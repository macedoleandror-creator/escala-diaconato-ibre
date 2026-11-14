# Escala do Diaconato — Igreja Rocha Eterna

Aplicação web estática para organizar a escala mensal do diaconato e a escala do culto de Santa Ceia. A interface foi desenvolvida em português do Brasil e funciona em navegadores modernos, inclusive em dispositivos móveis.

## Funcionalidades

- Inscrição de diáconos e diaconisas em cultos de quarta-feira e domingo.
- Seleção de função por culto, com limites de vagas e de inscrições por pessoa.
- Escala especial para o culto de Santa Ceia, com funções e limites próprios.
- Visualização compartilhada das inscrições usando Firebase.
- Área administrativa para alterar o mês e as configurações da escala, além de remover inscrições.
- Exportação das escalas mensal e de Santa Ceia como imagens JPG.
- Modo local com armazenamento no navegador quando o Firebase não puder ser iniciado.

## Como usar

1. Abra o site publicado.
2. Escolha seu nome na lista.
3. Marque os cultos em que pode servir e selecione uma função para cada um.
4. Clique em "Entrar na escala". Para a Santa Ceia, selecione seu nome e uma função na seção correspondente.
5. Use os botões de download para gerar as imagens JPG das escalas.

A aplicação aplica limites de vagas e restringe a inscrição de cada pessoa a dois cultos no mês. A escala da Santa Ceia tem limites específicos por função. As regras e listas de nomes estão definidas no arquivo `index.html`.

## Executar localmente

Não há etapa de build nem dependências de pacote. Basta servir o diretório como um site estático. Por exemplo, com Python:

```bash
python -m http.server 8000

Depois, acesse:

http://localhost:8000

Também é possível abrir index.html diretamente em um navegador, mas um servidor local é recomendado para testar o comportamento da página com mais fidelidade.

Firebase e dados compartilhados
A aplicação carrega Firebase compat v10.12.2 via CDN e usa Firebase Authentication e Cloud Firestore. A configuração do projeto está no objeto FIREBASE_CONFIG dentro de index.html.

Para configurar outro projeto Firebase:

Crie um projeto Firebase e registre uma aplicação Web.
Atualize FIREBASE_CONFIG em index.html com a configuração da aplicação.
Ative o Cloud Firestore e o método de autenticação por e-mail e senha.
Crie a conta administrativa no Firebase Authentication.
Configure regras do Firestore para proteger as inscrições e as configurações.
O app usa a coleção signups para inscrições e o documento settings/main para as configurações do mês. Sem conexão com o Firebase, os dados ficam no localStorage do navegador e não são compartilhados entre dispositivos.

Observação importante: a autenticação e os controles de administrador na interface não substituem as regras de segurança do Firestore. As regras do banco devem garantir a segurança no servidor.

Publicar no GitHub Pages
No GitHub, acesse Settings → Pages.
Escolha a origem de publicação (por exemplo, a branch main e a pasta raiz /).
Salve e aguarde a publicação do site.
Confirme que o Firebase está configurado e que as regras do Firestore permitem o funcionamento esperado no domínio publicado.
Como o repositório contém uma página estática na raiz, não é necessário configurar um processo de build.

Tecnologias
HTML
CSS
JavaScript
Firebase Authentication
Cloud Firestore
Canvas do navegador para geração de imagens JPG
Licença
Nenhuma licença foi identificada neste repositório. Consulte o proprietário antes de reutilizar ou distribuir o código.


If you want, I can also produce:
- a more polished bilingual version (PT-BR + English),
- a shorter project README,
- or a version optimized for GitHub Pages/landing page presentation.
