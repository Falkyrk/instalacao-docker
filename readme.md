# Instalação do Docker Desktop no Linux Ubuntu 22.04

## A instalação foi feita em uma máquina virtual usando VirtualBox

### VirtualBox
!["Virtualbox"](data:image/jpeg;base64,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)

    VirtualBox é um software de virtualização desenvolvido pela empresa Innotek depois comprado pela Sun Microsystems que posteriormente foi comprada pela Oracle que, como o VMware Workstation, visa criar ambientes para instalação de sistemas distintos.

    https://www.virtualbox.org/wiki/Downloads

    ### Após a instalação e criação da máquina virtual para o sistema Ubuntu, você deve acessar as configurações do virtualbox em sistema, clicar na guia processador e habilitar "Habilitar VT-x/adm-V aninhado

### Linux Ubuntu 22.04

    Ubuntu é um sistema operacional ou sistema operativo de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo. Esta distribuição Linux é desenvolvida pela Canonical Ltd

    https://ubuntu.com/download/desktop

### Docker

    Docker é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração.

## Configuração e instalação de ambiente

### Pós-instalação do Linux

    Após a instalação do linux Ubuntu 22.04, você deve executar alguns comandos para atualizar o sostema e deixa-lo preparado para a instalação do docker.

### Atualização dos pacotes

    ```console
    $ sudo apt update
    ```

### Atualização do sistema

    ```console
    $ sudo apt upgrade
    ```

### Reiniciar o sistema

    ```console
    $ reboot
    ```

### Instalação do Docker Desktop

    Download do Docker desktop
    https://www.docker.com/products/docker-desktop/

    Na pasta(diretorio) download localize o arquivo docker-desktop e assim você pode instalar de duas maneiras, sendo:
    1 - Clicar com o botão direito do mouse sobre o arquivo e escolher Software install

    2 - Abrir o terminal do linux e ir até a pasta(diretório) download e executar o comando de instalação:
        ```console
        $ sudo apt install ./docker-desktop-4.10.1-amd64.deb
        ```
    ###Caso retorne a mensagem de erro referente ao docker-ce e/ou docker-cli, execute os comandos abaixo:
        ```console
        $ sudo apt-get update

        $ sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
        ```
    ### Adicionar as chaves GPG oficiais do docker
        ```console
        $sudo mkdir -p /etc/apt/keyrings
        $curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
        ```
    ### Use o comando abaixo para carregar o repositorio de pacotes
        ```console
        $echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    ```

    ### Instalação do Docker Engine
    ```console
    $sudo apt-get update
    $sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
    ```

    ### Após a instalação das dependencias você deve executar o comando de instalação do docker desktop
        ```console
        $ sudo apt install ./docker-desktop-4.10.1-amd64.deb
        ```

## Instalando a imagem e o Container de Mysql no docker

### Vamos usar volume neste exemplo

    Crie uma pasta(diretorio) chamada dta_docker no home do usuario, execute o seguinte comando:
    ```console
    $ docker run --name servidor-mysql -v ~/data_docker:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:8.0.29
    ```
    Agora, abra o docker-desktop e veja o seu container rodando.
