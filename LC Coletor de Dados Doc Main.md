# LC Coletor de Dados V2

O LC Coletor de Dados V2 é a segunda versão do nosso aplicativo IOS/Android voltado para a conferência de produtos/estoque, desenvolvido para facilitar e agilizar esse processo. Ele possibilita a importação de um arquivo de conferência seguindo o modelo de montagem ```<CODIGO_INTERNO, CODIGO_DE_BARRAS, PRODUTO_NOME>```, sendo possível também definir essas opções nas configurações do aplicativo para melhor se adaptar ao seu caso de uso.

![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/fe619daf-da26-49a3-93c0-7647daeee0a2) ![image](https://github.com/lc-sistemas/LC_Coletor_de_dados_APP_V2/assets/147434228/eb6534f8-70ff-436b-b07f-b5b30649e44b)

# Entendendo arquitetura:

## Setup de ambiente: 

- ```IDE de codigo nativo e emulação:``` android studio (ultima versao disponivel) |
link: https://developer.android.com/studio?gad_source=1&gclid=CjwKCAiAlcyuBhBnEiwAOGZ2S5fcKCMNgdZq0Ut1_Vibxl6M2az1zD6MHKYfhvvouvn7GwxdQKhV4hoCUjUQAvD_BwE&gclsrc=aw.ds&hl=pt-br
- ```IDE de codigo React Native - TypeScript:``` VS Code (Ultima versão disponivel) |
link: https://code.visualstudio.com
- ```Versão do Java:``` JDK 11 |
link: https://drive.google.com/file/d/145RKIOhMsyhlXIwf7gkNg4rGPtIXW-a3/view?usp=sharing
- ```Versionamento:``` Git (logado com as credenciais da empresa "@lcsistemas.com.br");
- ```Versão do Node.js:``` versão 16.15.1 |
link: https://drive.google.com/file/d/1SmIfCVLXfw6vijyByhpu-3kV0hKwop_h/view?usp=sharing | pasta compartilhada: "\\\\192.168.1.16\lc_desenvolvimento\FABRICIO\node-v16.15.1-x64.msi".

## Estrutura de Projeto:

- ```./src/@types:``` Armazena toda a tipagem das variáveis responsáveis pela navegação.
- ```./src/assets:``` Armazena todos os arquivos utilizados, por exemplo, imagens, áudios e arquivos de texto.
- ```./src/components:``` Armazena todos os componentes globais.
- ```./src/databases:``` Armazena todos os arquivos relacionados ao banco de dados.
- ```./src/interfaces:``` Armazena todas as interfaces globais de tipagem.
- ```./src/provider:``` Armazena todas os providers disponiveis;
- ```./src/routes:``` Armazena todos os métodos de rotas.
- ```./src/screens:``` Armazena todas as telas e seus componentes exclusivos.
- ```./src/services:``` Armazena os serviços externos.
- ```./src/storage:``` Armazena os arquivos responsáveis pelo armazenamento (Cache).
- ```./src/util:``` Armazena todas as funções utilitárias e outros métodos.
- ```./src/App.tsx:``` Arquivo de montagem do aplicativo.

Detalhes sobre os componentes:
https://github.com/CassioNathan/teste/blob/main/Componentes.md
