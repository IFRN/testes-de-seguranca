# Testes de Segurança

## Introdução

Para iniciar o TP, você precisará clonar o repositório do projeto e garantir que está na pasta raiz do mesmo. Antes de seguir para a execução dos contêineres, certifique-se de que o Docker está instalado e em execução na sua máquina. Se estiver tudo certo, siga os passos abaixo:

1. Clone o repositório do projeto:

   ```bash
   git clone https://github.com/IFRN/testes-de-seguranca.git
   cd testes-de-seguranca
   ```

2. Inicie os contêineres necessários executando o comando:

   ```bash
   docker compose up -d
   ```

3. Após a execução bem-sucedida do comando, acesse os seguintes endereços no seu navegador:

   - [http://127.0.0.1:8000/api/doc/](http://127.0.0.1:8000/api/doc/) - Para acessar a documentação da API. Algumas falhas de segurança podem ser exploradas diretamente por aqui ou através de um cliente REST, como Postman, Insomnia, ou Hopscotch.
   - [http://127.0.0.1/](http://127.0.0.1/) - Para acessar o frontend da aplicação.

### Acesso ao Sistema

Cada aluno da turma já possui um usuário cadastrado no sistema. Para fazer login, utilize o número da sua matrícula como nome de usuário e a senha padrão 123. Esse acesso inicial permitirá que você explore as vulnerabilidades do sistema e responda às questões propostas no TP.

### Acesso à Documentação da API

Ao acessar a documentação da API em http://127.0.0.1:8000/api/doc/, você precisará fazer login através do Swagger para testar os endpoints protegidos. Utilize o botão "Authorize" localizado no canto superior direito da interface Swagger, e insira seu access token que pode ser conseguido através do endpoint /login/

> Ao explorar as vulnerabilidades e responder às questões, envie suas respostas através do [formulário](https://forms.gle/8ZtmDGKp9bNX3xv1A). Não se esqueça de utilizar seu e-mail @escolar.ifrn.edu.br ao submeter o formulário.

## Questões

1. Imagine que você é um detetive da segurança e conseguiu se infiltrar no sistema da Plácido Drive. Utilize um SQL Injection para acessar a lista de todos os usuários. Seu objetivo é verificar se há algum usuário que não deveria estar lá. _Dica: existe um endpoint que deveria retornar os dados só do seu usuário, mas se usado corretamente poderá trazer informações que deveriam ser sigilosas!_

   - O invasor colocou uma mensagem no lugar de seu nome completo, qual a mensagem?
   <br>
   <details>
   <summary>Dica forte</summary>
         Acesse o <a href="#material-apoio">material de apoio</a> de injeção de SQL para saber como fazer essa questão.
   </details>

2. Você descobriu um usuário que parece estar fora do lugar. Agora, é hora de descobrir seu nome de usuário. Os relatórios indicam que o invasor deixou uma mensagem na raiz da aplicação. _Dica: o endpoint de exclusão de arquivos expõe uma vulnerabilidade de Command Injection, aproveite-se dessa falha para tentar encontrar alguma pista por lá!_

   - Qual o nome de usuário (matrícula) do invasor?
   <br>
   <details>
   <summary>Dica forte</summary>
       Acesse o <a href="#material-apoio">material de apoio</a> de injeção de comandos para saber como fazer essa questão.
   </details>

3. Agora que você descobriu qual o username do usuário malicioso, encontre qual o arquivo que ele fez upload. Você precisa entrar na conta dele alterando a senha de acesso! _Dica: Existe uma grave falha na implementação da funcionalidade de alterar senha, talvez ela permita que você troque a senha do usuário!_

   - Qual foi o nome do arquivo enviado por ele?

4. Agora é só entrar na conta do usuário malicioso e fazer download do arquivo que ele enviou. Lá estará o código secreto para completar a tarefa!

   - Qual foi a mensagem secreta final deixada pelo nosso invasor?

### <span id="material-apoio">Material de Apoio</span>

Lembre-se de acessar o material de apoio para realizar o TP, pode ser de grande ajuda!

- [Como fazer injeção de SQL - Guia Básico](materiais/SQLInjection.md)
- [Como fazer injeção de comandos - Guia Básico](materiais/CommandInjection.md)

### Outro

Caso prefira, acesse essa atividade em [PDF](assets/TP3%20-%20Testes%20de%20Segurança.pdf)
