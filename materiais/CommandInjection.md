# Command Injection - Guia Básico

## Introdução

Command Injection é uma vulnerabilidade que ocorre quando um atacante consegue executar comandos arbitrários no sistema operacional através de uma aplicação vulnerável. Isso acontece quando a aplicação passa dados não confiáveis diretamente para um interpretador de comandos.

## Como Funciona

### 1. Entrada de Dados

A vulnerabilidade ocorre quando a aplicação aceita entrada do usuário e a utiliza para construir comandos do sistema operacional sem validação adequada.

### 2. Construção do Comando

A aplicação constrói um comando do sistema operacional usando a entrada do usuário. Se a entrada não for tratada corretamente, comandos maliciosos podem ser inseridos.

#### Exemplo Vulnerável

```python
import os

user_input = "diretorio"
os.system("ls " + user_input)
```

Se o atacante inserir `diretorio; rm -rf /`, o comando se torna:

```sh
ls diretorio; rm -rf /
```

### 3. Execução do Comando

O sistema operacional executa o comando modificado, que pode resultar em execução de comandos arbitrários, comprometendo a segurança do sistema.

### 4. Comandos que podem ser úteis em um Command Injection

- `ls`: Lista arquivos e diretórios.
- `cat`: Exibe o conteúdo de arquivos.
- `grep`: Pesquisa por padrões em arquivos.
- `find`: Encontra arquivos e diretórios.
- `nc` (Netcat): Ferramenta de rede para leitura e escrita em conexões de rede.
- `curl` ou `wget`: Ferramentas para transferir dados de ou para um servidor.
- `nmap`: Ferramenta de varredura de rede.
- `ssh`: Conecta-se a um servidor remoto via SSH.
- `tar` e `zip`: Ferramentas para compactar e descompactar arquivos.
