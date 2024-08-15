# Testes de Segurança

Para iniciar o TP, você precisará executar dois contêineres. Certifique-se de que o Docker está em execução em sua máquina e execute os seguintes comandos:

```bash
docker run -ti -d -p 8000:8000 qajuda/vulneravel
docker run -ti -d -p 80:80 qajuda/vulneravel-frontend
```

Depois de executar os comandos, acesse os seguintes endereços no seu navegador:

- [http://127.0.0.1:8000/api/doc/](http://127.0.0.1:8000/api/doc/) - Para acessar a documentação da API (algumas falhas só poderão ser testadas aqui ou com um cliente REST, como Postman, Insomnia, Hopscotch, etc.)
- [http://127.0.0.1/](http://127.0.0.1/) - Para acessar o frontend da aplicação

> Envie suas respostas no [formulário](https://forms.gle/8ZtmDGKp9bNX3xv1A)
> Use seu e-mail @escolar.ifrn.edu.br

## Questões

1. Imagine que você é um detetive da segurança e conseguiu se infiltrar no sistema da Plácido Drive. Utilize um SQL Injection para acessar a lista de todos os usuários. Seu objetivo é verificar se há algum usuário que não deveria estar lá. _Dica: existe um endpoint que deveria retornar os dados só do seu usuário, mas se usado corretamente poderá trazer informações que deveriam ser sigilosas!_

   - O invasor colocou uma mensagem no lugar de seu nome completo, qual a mensagem?

   <details>
   <summary>Dica forte</summary>
       Acesse o <a href="#material-apoio">material de apoio</a> de injeção de SQL para saber como fazer essa questão.
   </details>

2. Você descobriu um usuário que parece estar fora do lugar. Agora, é hora de descobrir seu nome de usuário. Os relatórios indicam que o invasor deixou uma mensagem na raiz da aplicação. _Dica: o endpoint de exclusão de arquivos expõe uma vulnerabilidade de Command Injection, aproveite-se dessa falha para tentar encontrar alguma pista por lá!_

   - Qual o nome de usuário (matrícula) do invasor?

   <details>
   <summary>Dica forte</summary>
       Acesse o <a href="#material-apoio">material de apoio</a> de injeção de comandos para saber como fazer essa questão.
   </details>

3. Agora que você descobriu qual o username do usuário malicioso, encontre qual o arquivo que ele fez upload. Você precisa entrar na conta dele alterando a senha de acesso! _Dica: Existe uma grave falha na implementação da funcionalidade de alterar senha, talvez ela permita que você troque a senha do usuário!_

   - Qual foi o nome do arquivo enviado por ele

4. Agora é só entrar na conta do usuário malicioso e fazer download do arquivo que ele enviou. Lá estará o código secreto para completar a tarefa!

   - Qual foi a mensagem secreta final deixada pelo nosso invasor?

### <span id="material-apoio">Material de Apoio</span>

    Lembre-se de acessar o material de apoio para realizar o TP, pode ser de grande ajuda!

    - [Como fazer injeção de SQL - Guia Básico](materiais/SQLInjection.md)
    - [Como fazer injeção de comandos - Guia Básico](materiais/CommandInjection.md)

### Outro

    Caso prefira, acesse essa atividade em [PDF](assets/TP3%20-%20Testes%20de%20Segurança.pdf)
