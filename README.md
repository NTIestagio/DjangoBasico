# Django Básico

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
    * Cria-se o ambiente virtual, no SO Windows, através do comando (prompt):
    
        ``` prompt
            > pythom -m venv <caminho absoluto (ou relativo) do direitório a ser criado>
        ```
    
    * O comando cria o diretório do ambiente virtual python, colocando os componentes necessários dentro. Veja o exemplo abaixo da criação do ambiente "ambVirt1":

        ![venvCriado](venv1.png)
    
    * Pode-se criar um ambiente virtual a partir da ferramenta VIRTUALENV. Sua instalação é realizada a partir do comando:

        ``` powershell
            > pip install virtualenv
        ```

        A consulta da versão pode ser realizada a partir do comando:

        ``` powershell
            > virtualenv --version
        ```

    * Cria-se um ambiente virtual no diretório atual com a ferramenta virtualenv a partir do comando (prompt):

        ``` powershell
            > virtualenv <nome-do-ambiente>
        ```

        ![virtualenv](virtualenv1.png)

    * Obs.: O pycharm faz a criação automática do ambiente do projeto nos casos dos novos projetos. Solicitanto apenas que o usuário informe o interpretador base para o projeto (preferencialmente 3.7.7).

        ![venvNovoProjeto](pycharm1.png)

    * A ativação do ambiente pode ser feita a partir do próprio terminal do pycharm, via prompt ou powershell. Usualmente, o terminal do pycharm abre o prompt de comando do Windows já utilizando o ambiente ativado, caso o projeto tenha sido criado a partir da opção de novo ambiente virtual assinalada. Isso pode ser verificado a partir da própria indicação na linha de comando.

        ![terminalPycharm](pycharm2.png)

    * Caso não o ambiente não esteja ativado, a ativação pode ser feita manualmente executando-se o script "activate" no diretório "Scripts" contido no diretório do ambiente a ser utilizado.

        * Para *prompt* de comando:

            ``` command prompt
                (...)\<nome-do-ambiente>\Scripts> activate 
            ```

        * Para *powerShell*:

            ``` powershell
                (...)\<nome-do-ambiente>\Scripts> activate.ps1 
            ```
        
        * O *powerShell* pode apresentar uma mensagem de erro referente a impossibilidade de execução de scripts. Para solucionar o problema, altere a política de execução de script ao powerShell através do comando abaixo:
        
            ``` powershell
                > Set-ExecutionPolicy Unrestricted
                > S
            ```

            Em seguida realize a ativação pelo comando:

            ``` powershell
                (...)\<nome-do-ambiente>\Scripts> activate.ps1 
            ```
        
1. **Instalando Django**

    * Para instalar uma versão oficial específica (no caso a versão 3.2.9 adotada pelo NTI) do Django no diretório do projeto, utilize o seguinte comando (prompt) a partir do terminal do pycharm:

        ``` powershell
            (...)\> python -m pip install Django==3.2.9
        ```
    
    * Observa-se a finalização da instalação dos componentes:

        ![djangoinstall](django1.png)

    * Pode-se observar as bibliotecas instaladas no ambiente a partir do comando (prompt):

        ``` powershell
            (...)\> pip freeze
        ```

    * Sendo exibidas como abaixo:

        ![pipFreeze](django2.png)

    * Obs. Aconselha-se redirecionar a saida do comando freeze para um arquivo de requiments.txt:

        ``` powershell
            (...)\> pip freeze > requiriments.txt
        ```
1. **Criando um projeto Django

    * Utilize o comando abaixo para criar o projeto Django dentro do diretório do projeto:

        ``` powershell
            (...)\> django-admin startproject <nome-do-projeto> .
        ```
    
    * Observe que a ferramenta cria os diretórios referentes ao projeto Django:

        ![venvNovoProjeto](pycharm1.png)

1. **Criando uma aplicação Django**
    
    * Utilize o comando abaixo para criar uma aplicação Django dentro do diretório do projeto:

        ``` powershell
            (...)\> django-admin startapp <nome-da-app>
        ```
    
    * Observe que a ferramenta cria os diretórios referentes a aplicação Django (foi utilizado o nome 'core' para aplicação):

        ![djangoAPP](django3.png)

    * Dentro do diretório do **projeto Django** (não no diretório da APP), faça a inclusão da aplicação no arquivo "settings.py" em "INSTALLED_APPS". Também acrescente a lista de "TEMPLATES" o diretório "templates".

        ![installed-apps](django4.png)
    
    
        ![templates](django5.png)
    
1. Projetos vs. Aplicações Django

    * O Django abrange um projeto, que representa todo o escopo, e aplicações, responsáveis pelas tarefas específicas.

1. Padrão MTV do Django

    * MVT significa Model-View-Template. Às vezes também é referido como MTV (Model-Template-View). MVT é um padrão de design ou arquitetura de design que o Django segue para desenvolver aplicações web. É um pouco diferente do padrão de design MVC (Model-View-Controller) comumente conhecido.
    * O 'Model' gerencia os dados e é representado por um banco de dados. O 'model' é basicamente uma tabela de banco de dados.
    * A 'View' recebe solicitações HTTP e envia respostas HTTP. A 'view' interage com um modelo e um template para concluir uma resposta.
    * O 'Template' é basicamente a camada front-end e o componente HTML dinâmico de uma aplicação Django.

    ![mvt](django6.png)
    
1. Configurações do Django e arquivo 'settings.py'

    * Importante: sempre que for utilizar os comandos de gerenciamento dos projetos Django certifique-se de executá-los no mesmo diretório do arquivo 'manage.py'. Para isso, verifique no terminal pycharm:
        
        * no linux:
        
            ``` powershell
                (...)\> ls
            ```

        * ou no windows:

            ``` powershell
                (...)\> dir
            ```
        
        Como resultado deverão ser informados os arquivos e diretórios contindos no diretório atual, devendo estar incluído entre eles o arquivo 'manage.py'.

    * Inicializando o servidor:
    
        ``` powershell
            (...)\> python3 manage.py runserver
        ```

        ``` powershell
            (...)\> python manage.py runserver
        ```

        ![mvt](django7.png)
    
        * obs. para encerrar o servidor aperte <control+c>
    
    * No arquivo 'settings.py' dentro do projeto Django criado, é possivel fazer as configurações de ligua (alteração de en-us para pt-br), permissõe de host e debug:

    ![mvt](django9.png)
    
    ![mvt](django8.png)
    
    * Observe que ao cliclar no endereço fornecido ao ser inicializado o servidor (geralmente loopback), será exibida a seguinte página (já em sua versão traduzida, caso tenha sido feita a alteração acima):

    ![mvt](django10.png)
    
1. Criando uma view no app Django

    * A criação de views para o app Django é feita a partir do arquivo 'views.py' localizado no diretório da aplicação.

    ![criarView](view1.png)
    
1. Adicionando Rotas e URLs

    * As rotas para as views de aplicações são gerenciadas a partir do arquivo 'urls.py' no diretório do projeto Django.
    * Faça a importação das funções relativas a aplicação a ser referenciada. A seguir insira os paths relativos a cada views de acordo com a hierarquia concebida.

    ![urls](urls1.png)
    
    * IMPORTANTE! Caso haja tentativa de acesso a uma view que não exite, caso tenha sido utilizada as configurações acima, as rotas criadas serão todas exibidas (todas as rotas constantes no arquivo urls.py pertencente ao diretório do projeto), o que pode representar uma falha de segurança:

    ![rotas](rotas1.png)
    
    * Sugere-se dessa forma a criação de um arquivo de rotas (urls.py) dentro da aplicação e apenas um path referenciando a esse arquivo dentro do arquivo de rotas do projeto através da função include().

    ![rotas](rotas2.png)
    
    ![urls](urls2.png)
    
1. Criando o diretório de templates e arquivos html para aplicação

    * Crie um diretório 'templates' dentro do diretório da aplicação e dentro dele os arquivos html referente as views anteriormente criadas (no exemplo foram utilizados os arquivos 'index' e 'contato'.
    
    ![templates](temp1.png)
    
    * A variável 'context' dentro da view é passada para o template a partir da função render() da view. As informações passadas ficam disponíves para utilização do template (obs. o servidor deve estar em execução para visualização da página gerada).

    ![viewContext](view2.png)
    
    ![index](temp2.png)
    
1. Model da aplicação

    * Um model é uma fonte única e definitiva de informações sobre os seus dados. Ele contém os campos e comportamentos essenciais dos dados que você está armazenando. Em geral, cada modelo mapeia uma única tabela no seu banco de dados.
    * O arquivo 'models.py' representa uma classe python, enquanto cada atributo do model representa um campo de base de dados.
    * Foram criados os campos nome, preço e estoque. Cada compo criado corresponde a um atributo de classe, que por sua vez mapeia uma coluna do banco de dados.

    ![model](mod1.png)
    
    * Finalizada a criação do model, procede-se a criação do arquivo de migration referente ao modelo no diretório 'migrations' da aplicação através do comando:
    
        ``` powershell
            (...)\<nome-do-projeto> python manage.py makemigrations
        ```
    
    obs.: a criação da migration depende a inclusão da aplicação no arquivo settings.py do projeto.
    
    ![criandoMigration](mod2.png)
    
    Realizada a operação, pode ser verificada a criação do arquivo migration na aplicação:
    
    ![criandoMigration](mod3.png)
    
    * Criada a migration, é necessaria sua aplicação a partir do comando:

        ``` powershell
            (...)\<nome-do-projeto> python manage.py migrate
        ```
    
    * É exibida então a mensagem de aplicação das migrations pendentes:
 
        ![aplicandomigration](mod4.png)
    
1. Área administrativa e arquivo 'admin.py'

    * Observe que existe uma interface administrativa para projeto:

        ![interfAdmin](admin1.png)
        
    * É necessaria a criação de um usuário administrativo (administrador do sistema) para o projeto. Deve ser fornecido um nome de usuário, senha e email. Utiliza-se o comando:
        
        ``` powershell
            (...)\<nome-do-projeto> python manage.py createsuperuser
        ```
        
        ![criandoSU](admin2.png)
        
    * Finalizada a criação, é possivel realizar o login na área administrativa (com o servidor em execução):

        ![login](admin3.png)
        
    * Para que os campos referentes aos models sejam disponibilizados na área administrativa do site, é necessario realizar a alteração do arquivo admin.py da aplicação para incluir as referências aos models criados:

        ![login](admin4.png)
    
    * Veja que agora a área de administração do Site passa a exibir os modelos da aplicação criada. Sendo possível gerenciá-los a partir da interface de acordo com os atributos fornecidos:

        ![login](admin5.png)
        
        ![login](admin6.png)

    * O gerenciamento da base de dados criada passa então para a interface de administração do Site. No exemplo, pode-se criar, alterar e deletar produtos e clientes.
    * Alterações da interface de exibição dos models criados para a aplicação podem ser realizadas a partir do arquivo 'admin.py' da aplicação. A forma de exibição dos dados cadastrados pode ser alterada a partir de uma classe admin.ModelAdmin() com o uso de list_display:

        ![login](admin7.png)
        
1. Django Shell

    * A lista de comandos disponível para o manage.py é exibida a partir do comando 'python manage.py'.
    * O comando 'python manage.py help <subcomando>' exibe as informações de ajuda para determinado comando disponível
        
        ``` powershell
            (...)\<nome-do-projeto> python manage.py help
            (...)\<nome-do-projeto> django-admin help
        ```
    * O comando shell abre um terminal python interativo. Sendo possivel gerenciar os componentes do framework, como banco de dados a partir de cli gerado.
    
        ``` powershell
            (...)\<nome-do-projeto> python manage.py shell
            (...)\<nome-do-projeto> django-admin shell
        ```
    * Pode-se importar as classes criadas:
    
        ``` powershell
            >>> from core.models import Produto
            >>> from core.models import Cliente
            >>> from core.views import index
            >>> dir(Produto) //exibe os atributos do objeto
            >>> dir(index)
        ```
    * Instanciar novos objetos e salva-los no banco de dados:
    
        ``` powershell
            >>> produto = Produto(nome='Atari 2600', preco=199.50, estoque=100)
            >>> produto.save()
            >>> cliente = Cliente(nome='Maria', sobrenome='da Silva', nome='mariadasilva@gmail.com')
            >>> cliente.save()
        ```
     * É possível acessar os atributos e alterá-los. Sendo possivel também removê-lo a partir do método 'delete':
    
        ``` powershell
            >>> cliente.nome= 'Maria Severina'
            >>> cliente.save()
            >>> cliente.delete()
        ```

1. Apresentando os dados do BD no template
    
    * Importe a classe models na views.py do app, e acesse seus objetos e atributos:
        
        ``` python
            from .models  import Produto
        ```
    
    * Para resgatar objetos para exibição, utiliza o metodo 'objects':
        
        ``` python
            produtos = Produto.objects.all()#resgata uma série de objetos do tipo 'Produto', do BD
            produtoUnit = Produto.objects.get(pk=pk)#resgata um objeto especifico do tipo 'Produto' com atributo pk correspondente ao parametro pk passado
        ```
        
        * Alternativamente, pode-se utilizar o método 'get_object_or_404(Produto, pk=pk)' para exibir a página html404 caso não consiga resgatar o objeto a ser utilizado para geração do template na view.
    
        * Os objetos resgatados na 'views.py' podem ser utilizados dentro dos templates a partir do 'context' de cada método criado para um respectivo template.

1. Arquivos estáticos
    
    * Para utilizar arquivos estáticos de CSS, JS e imagens nos templates, insira '{% load static %}' no template:
        
        ``` html
            <link rel="stylesheet" href="{% static 'css/estilos.css' %}"><!-- faz referencia a css -->
            <img src="{% static 'images/logo.png' %}" alt="My image"><!-- faz referencia a imagens -->
            <script type="text/javascript" src="{% static 'js/script.js' %}"></script><!-- faz referencia a js -->
        ```
        
    * Observe que o diretório 'static' deve ser criado dentro do diretório correspondente a aplicação. No exemplo acima, o diretório 'static' contém os subdiretórios css, images e js, cada um contendo os arquivos a que são feitas as referências acima.
    * Tais diretórios das aplicações são utilizados apenas no modo desenvolvedor. Quando da publicação do projeto, tais arquivos são copiados para um diretório 'staticfiles' global, que contém arquivos referentes a todo o projeto e suas aplicações. De modo que o arquivo de *'settings.py'* deve ser acrescido com a variavel STATIC_ROOT, conforme abaixo:
    
        ``` python
            STATIC_URL = '/static/'#durante desenvolvimento debug==true
            STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')#durante produção debug==false
        ```
    
    * O diretório 'staticfiles' é criado automaticamente a partir do comando:
         
        ``` python
            > python manage.py collectstatic
        ```
    
    * Template para erro 404 personalizado pode ser gerado criando-se o arquivo '404.html' nos templates da aplicação
    
1. Publicando os projetos na internet
    
    * Instale as ferramentas whitenoise e gunicorn:
    
        ``` shell
            > pip install whitenoise gunicorn
        ```
        
        * Deve ser exibida a mensagem de sucesso da instalação, por exemplo:
        
            ``` shell
                Installing collected packages: whitenoise, gunicorn
                Successfully installed gunicorn-20.1.0 whitenoise-6.0.0
            ```
    * Antes de efetuar login no HEROKU pela rede, realize o set do HOMEDRIVE no windows CMD
        
            ``` shell
                > set HomeDrive=C:\Users\<nome-do-usuario>
            ```
