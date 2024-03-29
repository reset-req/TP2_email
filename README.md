# TP2 E-Mail

## Pré-requisitos
Pré-requisitos: [openssh-client](https://www.ssh.com/ssh/command/)

A instalação do openssh-client pode ser feita no linux pelo CLI:
`sudo apt-get install openssh-client`
    
## Introdução

Foi disponibilizada uma maquina virtual, **Linux**, para o uso desta atividade.
O acesso será feito via ***ssh*** e é possível usar [CLI](https://www.suse.com/c/working-command-line-basic-linux-commands/)
para operar o sistema.

## Acesso
1. `ssh usuario@ip`
    1. requisitar acesso para o professor ou ao estudante responsável.

1. Acessar e checar se todos os pré-requisitos instalados, solicitar instalação caso necessária.
    1. Checar se existe uma pasta chamada **Maildir**, `ls`
    ![Comando ls](/images/ls.png)
    
    1. Caso **não** exista, executar o comando `mkdir Maildir`
    ![Comando mkdir](/images/mkdir.png)
    
    1. Provavelmente você verá que tem mais algumas pastas dentro de **Maildir**
    ![Conteudo maildir](/images/maildir.png)
  
## Enviando E-mail
   O envio pode ser feito de duas formas, linha de comando ou por Telnet.
    
### Command Line
Basta ter um arquivo txt com o conteudo que você deseja enviar e executar o seguinte comando:


    `cat <caminho do txt> | mail -s '<assunto>' -r <remetente> <user@email.com>`
   -s: Assunto do email
   
   -r: Remetente, por padrão será o usuário em que está logado.
   
   user@email.com: A conta que se deseja enviar o email. Caso o destinatário seja outro usuário, da mesma máquina, basta colocar user@ubuntu16046 (ex.: admin@ubuntu16046).

### Telnet

Forma um pouco mais complicada, primeiro é necessário entrar na interface Telnet
![Interface Telnet](/images/telnet.png)

Depois é preciso logar no usuário, digitando EHLO <usuário>
![Login Telnet](/images/telnet_login.png)

Usar os comandos `mail from: <email>` e `rcpt to: <email>`
![Remetente Telnet](/images/telnet_remetente.png)

Para escrever a mensagem usaremos date para iniciar o texto e completaremos de acordo com o exemplo
usando o simbolo `.` sozinho seguido de ENTER para terminar a mensagem
![Email Telnet](/images/telnet_email.png)


## Visualizando E-Mails

Para visualizar e-mails na maquina usaremos o comando `mail` na qual seremos levados a interface de mail
![Mail](/images/mail.png)

Então é possível selecionar a mensagem digitando o número dela
![Mail](/images/mail_select.png)

O comando `h` mostra novamente a lista de mensagens
![Mail](/images/mail_display.png)

É possível deletar a mensagem digitando `d <número>`
![Mail](/images/mail_delete.png)

Digite `q` para sair da interface

## Acesso aos arquivos
Dentro do diretorio `~/Maildir` é possível encontrar os dados de envio e recebimento de email.
