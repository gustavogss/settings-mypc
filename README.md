# Configurações e Instalação de pacotes: 

## Instalação do Git e da chave SSH:

***Instalação do [Git](https://git-scm.com/)***

***Adicionando a chave SSH***
1. Abra o seu terminal e digite o comando abaixo:
   ```
    ssh-keygen -t rsa -b 4096 -C "gustavogss.dev@gmail.com"
   ```
2. Durante o processo irá aparecer escrito no terminal ***Enter a file in which to save the key***, basta pressione Enter para aceitar a localização padrão /home/you/.ssh/id_rsa   
3. Agora digite uma senha segura e confirme digitando novamente a mesma senha   
4. Ele criará duas chaves SSH dentro do arquivo ***cd ./ssh***, uma chave privada id_rsa e outra pública id_rsa.pub
5. Para adicionar sua chave ao ssh-agent, que é uma espécie de porteiro que possui as chaves de comunicação usando ssh. Digite o comando:
   ```
   eval "$(ssh-agent -s)"
   ```
 6. Ele irá retornar o processo no qual está rodando o nosso porteiro. ***Agent pid numero_do_seu_processo***
 7. Depois devemos dizer ao porteiro que nossa chave privada é válida, e para isso digitamos o comando:
    ```
    ssh-add ~/.ssh/id_rsa
    ```
    - Caso esteja dentro da pasta da chave basta digitar: ***ssh-add id_rsa***
      
 8. Adicionando a chave SSH na sua conta do GitHub:
    - No linux usamos um comando para copiar nossa chave. Funciona como um Ctrl+C e Ctrl+V. Que é o xclip, para instalá-lo digitamos o comando no terminal do linux:
      ```
      sudo apt-get install xclip
      ```
    - Para copiar a chave pública, a id_rsa.pub. Abra um novo terminal, e digite o comando:
      ```
      xclip -sel clip < ~/.ssh/id_rsa.pub
      ```
    - Agora vá la na sua conta do Github. E no canto direito da sua foto de perfil, clique em settings. Vá até SSH e GPG Keys e clique novamente.
    - Em SSH keys, clique no botão New SSH Key
    - Cole a chave que você copiou na descrição e dê um titulo para ela tipo ***pc-linux***
    - Clique em Adicionar SSH Key
    - Pronto, a partir de agora, ficará mais fácil fazer os seus clones e pull requests através do SSH
   
   ## Instalação e Configuração do ZSH:

   ## Atualização dos pacotes do snap:

   ## Instalação de utilitários:
   - [Zoom](#)
   - [Discord](#)
   - [Whats app](#)
      
   ## Instalação e Configuração do Node (nvm): 

   ## Instalação e Configuração do Java (sdkman):

   ## Instalação e Configuração do Docker e Docker-Compose:

   ## Instalação e Configuração do Ambiente de Desenvolvimento (VSCode):

   ### Implatanção do ambiente de desenvolvimento por stack, para evitar conflitos de plugins e ter uma melhor experiência e produtividade com configurações especificas para cada ambiente 
 
   ***Profile React***

   ***Profile React Native***

   ***Profile Android***

   ***Profile Flutter***

   ## Instalação e Configuração do Android Studio:

   ## Instalação e Configuração do React Native:

   ## Instalação e Configuração do Flutter:

   ## Instalação e Configuração do MySQL com Docker:

   ## Instalação e Configuração do MongoDB com Docker:

   ## Instalação e Configuração do Mac com Docker:

   ## Instalação do Gitflow e Processos de padronização de Commits:

   
   
 
