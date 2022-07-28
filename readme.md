# Instalação do Docker Desktop no Linux Ubuntu 22.04

## A instalação foi feita em uma máquina virtual usando VirtualBox

### VirtualBox
!["Virtualbox"](https://p7.hiclipart.com/preview/340/100/4/virtualbox-virtual-machine-operating-systems-virtualization-x86-linux-thumbnail.jpg)

    VirtualBox é um software de virtualização desenvolvido pela empresa Innotek depois comprado pela Sun Microsystems que posteriormente foi comprada pela Oracle que, como o VMware Workstation, visa criar ambientes para instalação de sistemas distintos.

    https://www.virtualbox.org/wiki/Downloads

    ### Após a instalação e criação da máquina virtual para o sistema Ubuntu, você deve acessar as configurações do virtualbox em sistema, clicar na guia processador e habilitar "Habilitar VT-x/adm-V aninhado

### Linux Ubuntu 22.04
!["Ubuntu"](https://icons.iconarchive.com/icons/martz90/circle/256/ubuntu-icon.png)

    Ubuntu é um sistema operacional ou sistema operativo de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo. Esta distribuição Linux é desenvolvida pela Canonical Ltd

    https://ubuntu.com/download/desktop

### Docker
!["Docker"](https://pics.freeicons.io/uploads/icons/png/15889022741579517836-512.png)

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
