# DjangoBasico

## Configurações iniciais

1. **Instalando python**
    
    * Adota-se por padrão a versão 3.7.7 do python no projetos do NTI. A versão pode ser baixada no [Site Oficial](https://www.python.org/downloads/release/python-377/), ou clicando diretamente [aqui](https://www.python.org/ftp/python/3.7.7/python-3.7.7-amd64.exe) caso esteja utilizando SO windows.
    * Obs. Lembre-se de associar a versão ao path durante o processo de instalação:

        ![versao](py2.png)
        
    * Observe-se que um sistema pode possuir mais de uma versão instalada. Para verificar a versão associada ao path, pode-se utilizar o comando no prompt:
    
        ```scrit
            > python --version
        ```
    * A versão será exibida abaixo:
    
        ![versao](py3.png)
    
1. **Instalando PyCharm**

    * Sugere-se a utilização do PYCHARM como IDE de trabalho. A versão mais recente pode pode ser baixada no [Site Oficial](https://www.jetbrains.com/pt-br/pycharm/download/#section=windows), ou clicando diretamente [aqui](https://www.jetbrains.com/pt-br/pycharm/download/download-thanks.html?platform=windows&code=PCC) caso esteja utilizando SO windows.
    * Siga o instalador proguindo sempre com as opções padrão já selecionadas.
    * Observe que há duas versões do PyCharm, uma gratuita (community) e ou paga (professional), para a qual deve ser adquirida licença.
    
1. **Criando e ativando um ambiente virtual python**

    * Aplicações em Python normalmente usam pacotes e módulos que não vêm como parte da instalação padrão. Aplicações às vezes necessitam uma versão específica de uma biblioteca, porque ela requer que algum problema em particular tenha sido consertado ou foi escrita utilizando-se de uma versão obsoleta da interface da biblioteca.
    * Isso significa que talvez não seja possível que uma instalação Python preencha os requisitos de qualquer aplicação. Se uma aplicação A necessita a versão 1.0 de um módulo particular mas a aplicação B necessita a versão 2.0, os requisitos entrarão em conflito e instalar qualquer uma das duas versões 1.0 ou 2.0 fará com que uma das aplicações não consiga executar.
    * A solução para este problema é criar um ambiente virtual, uma árvore de diretórios que contém uma instalação Python para uma versão particular do Python, além de uma série de pacotes adicionais.
    * A criação de um ambiente virtual python pressupõe logicamente a instalação prévia do python, vez que a aplicação pip é instalada juntamente com o python por padrão. A verificação da versão do pip instalada pode ser feita através do comando (prompt):

        ```
            > pip --version
        ```

    * A versão será exibida abaixo:
    
        ![versao](pip1.png)
    
    * Um ambiente virtual python pode ser criado em qualquer diretório da máquina. No entanto sugere-se a sua criação em diretório distinto daquele destinado ao projeto.
    * Cria-se o ambiente virtual, nos SO Windows, através do comando (prompt):
    
        ```
            > pythom -m venv <caminho absoluto (ou relativo) do direitório a ser criado>
        ```
    
    * O comando cria o diretório do ambiente virtual python, . Veja o exemplo abaixo da criação do ambiente "ambVirt1":

        ![venvCriado](venv1.png)
    
    * Obs. O pycharm faz a criação automática do ambiente do projeto nos casos dos novos projetos. Solicitanto apenas que o usuário informe o interpretador base para o projeto (preferencialmente 3.7.7).

        ![venvNovoProjeto](pycharm1.png)

    * A ativação do ambiente pode ser feita a partir do próprio terminal do pycharm, via prompt ou powershell. Usualmente, o terminal do pycharm abre o prompt de comando do Windows já utilizando o ambiente ativado. Isso pode ser verificado a partir da própria indicação na linha de comando.

        ![terminalPycharm](pycharm2.png)

    * Caso não o ambiente não esteja ativado, a ativação pode ser feita manualmente executando-se o script "activate" no diretório "Scripts" contido no diretório do ambiente a ser utilizado.

        * Para *prompt* de comando:

            ```
                (...)\<nome-do-ambiente>\Scripts> activate 
            ```

        * Para *powerShell*:

            ```
                (...)\<nome-do-ambiente>\Scripts> activate.ps1 
            ```
        
1. **Instalando Django**

    asdfasf

