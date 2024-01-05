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
      
   ## Atualização dos pacotes do snap:
   - Atualizando os pacotes do sistema operacional e o snap-store com uma linha de comando:
   ```
   sudo apt update && sudo apt full-upgrade -y && sudo apt autoremove -y && sudo apt autoclean && sudo snap refresh
   ```
   ## Instalação e Configuração do ZSH:

   1. Instalando o zsh:
      ```
       sudo apt install zsh
      ```
   2.  Verifique a versão do zsh, para ver se tudo ocorreu bem:
      ```
      zsh --version
      ```
   3. Instale o Oh My Zsh:
      - Primeiro instale o curl ***sudo apt install curl***
      - Depois instale o my zsh:
      ```
      sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
      ```
      - Ele te perguntará se deseja que o zsh se torne o shell padrão: digite Y e aperte <ENTER>
      - Feche o terminal e abra um novo para ver as atualizações. Se não houver alteração, reinicie seu computador.
      - Para facilitar a instalação de plugins, instale o Zinit com o comando:
        ```
        $ sh -c "$(curl -fsSL https://git.io/zinit-install)"
        ```
      - Após a instalação do Zinit, abra seu zshrc com o comando: ***sudo gedit ~/.zshrc*** e adicione as seguintes linhas no final do arquivo:
        ```
        zinit light zdharma/fast-syntax-highlighting
        zinit light zsh-users/zsh-autosuggestions
        zinit light zsh-users/zsh-completions
        ```
      - Salve o arquivo e feche, feche o terminal, e abra novamente o terminal para as atualizações serem instaladas.
      - Para mudar o tema do shell para o spaceship clone o repositorio com o comando:        
        ```
        git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1      
        ```
      - Crie um link simbólico:
        ```
        ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
        ```
      - Abra novamente seu arquivo .zshrc ***sudo gedit ~/.zshrc***
      - E na linha ZSH_THEME, adicone o nome do tema:
        ```
        ZSH_THEME="spaceship"
        ```
      -  No final do arquivo coloque essas configurações:
        ```
        SPACESHIP_PROMPT_ORDER=(
        user          # Username section
        dir           # Current directory section
        host          # Hostname section
        git           # Git section (git_branch + git_status)
        hg            # Mercurial section (hg_branch  + hg_status)
        exec_time     # Execution time
        line_sep      # Line break
        jobs          # Background jobs indicator
        exit_code     # Exit code section
        char          # Prompt character
         )
         SPACESHIP_USER_SHOW=always
         SPACESHIP_PROMPT_ADD_NEWLINE=false
         SPACESHIP_CHAR_SYMBOL=">"
         SPACESHIP_CHAR_SUFFIX=" "
        ```
      -  Salve o arquivo, feche. Feche o terminal e abra novamente para ver as atualizações      
            
   5. Abra um terminal para ver as novas atualizações.
      
   7. Pronto agora você não utilizará mais o shell bash, e sim o zhrc, para adicionar as novas configurações a partir de então, basta digitar o comando:
      ```
      sudo gedit ~/.zshrc
      ```    

   ## Instale os aplicativos através da Central de Aplicativos do Ubuntu:
   - Zoom 
   - Discord
   - Whats app
   - Telegram
      
   ## Instalação e Configuração do Node (nvm): 
   1. Instale o nvm com o comando:
      ```
      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
      ```
   2. Instale as variaveis de ambiente do nvm digitando o comando no terminal:
      ```
      export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
      [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
      ```
   3. Para verificar se tudo ocorreu bem digite o comando ***nvm -v***, ele irá mostrar a versão do nvm que instalou
      
   4. Para ver as versões remotas do node que temos, digite o comando:
      ```
      nvm ls-remote
      ```
   5. Para instalar a versão para digitar:
      ```
      nvm install v18.19.0
      ```
   7. Instale as versões LTS de longo prazo. Eu instalei as versões: v20.10.0, v18.19.0, v16.20.2, v14.21.3
      
   9. Para mudar de versão de uma forma mais pratica, defina aliases no final de seu arquivo zshrc.
       
   10. Com o arquivo zshrc aberto, no final de tudo, acrescente as linhas:
       ```       
      alias node14="nvm alias default v14.21.3"
      alias node16="nvm alias default v16.20.2"
      alias node18="nvm alias default v18.19.0"
      alias node21="nvm alias default v21.10.0"
       ```
   11. Salve e feche o arquivo.
       
   13. Toda vez que vou mudar de versão, basta digitar no seu terminal:
       ```
       node14 -> Para a versão 14 do node
       ```
       ```
       node16 -> Para a versão 16 do node
       ```
       ```
       node18 -> Para a versão 18 do node
       ```
       ```
       node21 -> Para a versão 21 do node
       ```      

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

   
   
 
