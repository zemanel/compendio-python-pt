Compêndio de recursos Python
============================

 ***Básico, bibliotecas e outras coisas fantásticas***

Licença de uso
--------------

Copyright 2013 José Moreira

Todo o conteúdo é de uso reservado ao autores e contribuidores.

É permita a livre utilização e reprodução por terceiros, para fins não comerciais.

Os autores e contribuidores não se responsabilizam por quaisquer danos materiais, não-materiais e / ou aumentos de produtividade resultantes da absorção da informação pertinente ao conteúdo.

Nenhum ser Humano, durante a escrita da informação aqui contida, foi afetado de forma física ou intelectual, por ato de violência ou sarcasmo extremo, em particular por [*Oryctolagus cuniculus*](http://pt.wikipedia.org/wiki/Coelho).

Introdução
----------

Costumo encontrar-me ocasionalmente com um estimado antigo professor de C, na voltinha de café noturna. Uma ocasião, o mesmo teve a infortunada ideia de me mostrar algum interesse em aprender Python. Como é de prever, sempre que me encontra a conversa tender a pender para o meu evangelismo do Python.

Encontrei-o hoje novamente e, dado que já não o via há algum tempo, perguntei se sempre tinha dado seguimento ao interesse por Python. Como ele referiu que não, por motivos de falta de tempo, disponibilizei-me a enviar-lhe um e-mail com alguns links com informação compilada sobre o assunto.

Como parte da conversa de hoje foi sobre alguma falta de conteúdos sobre o assunto na web em Português, decidi juntar o útil ao agradável e escrever um artigo sobre o assunto.

Algumas notas
-------------

* a ordem de listagem de alguns recursos **podem** ser altamente influenciadas pelas preferências do autor.
* serão exemplificados utilitários em ambiente OSX, mas regra geral as ferramentas são agnósticas de sistema operativo
e a respetiva página de documentação fará referências a outros sistemas operativos e é sempre o melhor recurso


Endereços oficiais
------------------

* Sítio oficial

    [http://python.org](http://python.org)

* Sítio oficial da documentação

    Ramo *2.x*: [http://docs.python.org/2/](http://docs.python.org/2/)

    Ramo *3.x*: [http://docs.python.org/3/](http://docs.python.org/3/)

* Índice / repositório de pacotes "Pypi"

    [http://pypi.python.org/pypi](http://pypi.python.org/pypi)

    Navegável online e utilizado como fonte para instaladores de pacotes Python.

Comunidade em Portugal
----------------------

* Sítio oficial

    [http://www.python.pt](http://www.python.pt)

* Google Plus

    [https://plus.google.com/108357965175724279344](https://plus.google.com/108357965175724279344)

* Google Groups (*mailing-list*)

    [https://groups.google.com/forum/#!forum/python-pt](https://groups.google.com/forum/#!forum/python-pt)

Comunidade no Brasil
--------------------

* Sítio oficial

    [http://python.org.br](http://python.org.br)

* Google Plus

    [https://plus.google.com/u/0/communities/103641722823086278652](https://plus.google.com/u/0/communities/103641722823086278652)

* Google Groups (*mailing-list*)

    [https://groups.google.com/forum/#!forum/python-brasil](https://groups.google.com/forum/#!forum/python-brasil)

* Wiki da comunidade

    [http://www.python.org.br/wiki](http://www.python.org.br/wiki)

Documentação comunitária; livros
--------------------------------

* Python para principiantes: [http://www.pythonforbeginners.com](http://www.pythonforbeginners.com)

    Sítio com vários artigos, agregados por categorias

* *The Hitchhiker’s Guide to Python!*: [http://docs.python-guide.org/en/latest/](http://docs.python-guide.org/en/latest/)

    Um compêndio de Python em Inglês (do qual, em parte surgiu, a ideia para este mesmo)

* *Dive into Python*

    Livro gratuito, com um intuito mais prático que teórico

    * Python *3.x*: [http://getpython3.com/diveintopython3/](http://getpython3.com/diveintopython3/)

    * Python *2.x*: [http://www.diveintopython.net](http://www.diveintopython.net)

Ferramentas básicas que fazem a diferença
-----------------------------------------

### pip

* Sítio oficial

    [http://www.pip-installer.org](http://www.pip-installer.org)

* Página de detalhe "Pypi" do Pip

    [http://pypi.python.org/pypi/pip](http://pypi.python.org/pypi/pip)

É uma ferramenta simples de utilizar, para várias funções, por exemplo:

**Instalar um (ou mais) pacotes**

    $ pip install nome_do_pacote_1 nome_do_pacote_2

**Instalar uma versão específica de um pacote, caso essa versão [ainda] esteja disponível no Pypi**

    $ pip install nome_do_pacote==1.0.1

**Atualizar (caso necessário) um pacote**

    $ pip install -U nome_do_pacote_1

**Desinstalar um pacote ou mais pacotes**

    $ pip uninstall nome_do_pacote_1

Uma funcionalidade excelente e muito usada, é o facto de se poder passar como parâmetro ao comando, o caminho de um ficheiro de texto que contenha, por linha, o nome e possivelmente versão, tal como no uso singular acima exemplificado, de uma lista de pacotes e desta forma o *pip* instala de forma automática todos os pacotes listados.

O formato / funcionalidade é chamado *[requirements file](http://www.pip-installer.org/en/latest/requirements.html)*.

Por exemplo, tendo o ficheiro de nome "requirements.txt" (nome standard não oficial de um tal ficheiro, mas não obrigatório) o seguinte conteúdo :

    # dependências do projecto X
    -e git+https://github.com/paramiko/paramiko#egg=

    # Utilitário de testes de unidade
    nose

    # Biblioteca de apoio a testes de unidade. Adiciona côr ao resultado das automatizações do Fabric
    -e git+https://github.com/bitprophet/rudolf#egg=rudolf

    # Biblioteca de apoio a testes de unidade.
    Fudge < 1.0

    # Gerador de documentação
    Sphinx >= 0.6

o resultado seria o seguinte:

* o pacote *paramiko* seria instalado no sistema Python através de *cloning* do Github.com
* seria instalada a versão mais recente [disponível no Pypi] do pacote *nose*
* seria instalada a versão mais recente [disponível no Pypi] do pacote *Fudge* mas inferior à versão *1.0*
* seria instalada a versão mais recente [disponível no Pypi] do pacote *Sphinx* caso seja superior à versão *0.6*
* todas as linhas começadas por *#* são ignoradas e usadas geralmente como comentários

Uma grande vantagem do uso de "requirement files", é o facto de serem facilmente geridos e comparáveis em sistemas de controlo de versão de código-fonte e são normalmente incluídos e mantidos junto com o código fonte do projeto a que se referem e assim se evita a dessincronização entre o código-fonte e as suas dependências.

É de notar que o [http://pypi.python.org/pypi](http://pypi.python.org/pypi) é o repositório oficial, o software em que corre é código-aberto e é possível criar instalações locais, sejam pessoais ou outras (empresariais), que possam ou não ter disponíveis todos os pacotes do repositório oficial.

Como nota final, não é incomum certas empresas publicarem os seus pacotes (em que [de-]compõem o seu software; geralmente proprietários) em repositórios privados e utilizarem o conjunto do(s) repositório(s) privado(s) + público(s), como fontes de instalação.

### virtualenv

* Página de detalhe "Pypi": [http://pypi.python.org/pypi/virtualenv/](http://pypi.python.org/pypi/virtualenv/)

Bibliotecas e conjunto de "scripts" de linha de comando que permitem a "virtualização" de instalações de Python.

Torna possível a criação de uma ou várias "instalações virtuais" de Python num sistema operativo, cada uma com o seu conjunto de pacotes e mesmo versões de Python diferentes (2.5, 2.7, 3.0).

Por exemplo, é muito comum os programadores de Python criarem uma instalação virtual por projeto, dado que dessa forma podem isolar as dependências de cada projeto (tal como ter versões diferentes do mesmo pacote em projetos diferentes).

Exemplificando, tendo a seguinte instalação de Python + *pip* no sistema:

    zemanel@victory ➜  ~  which python
    /usr/local/bin/python

    zemanel@victory ➜  ~  python --version
    Python 2.7.3

    zemanel@victory ➜  ~  which pip
    /usr/local/bin/pip

    zemanel@victory ➜  ~  pip --version
    pip 1.2.1 from /usr/local/lib/python2.7/site-packages/pip-1.2.1-py2.7.egg (python 2.7)

assumindo uma instalação *limpa*, é primeiro necessário a instalação do próprio pacote *virtualenv* no sistema operativo, neste caso através do *pip*:

    zemanel@victory ➜  ~  pip install virtualenv
    Downloading/unpacking virtualenv
      Real name of requirement virtualenv is virtualenv
      Using download cache from /Users/zemanel/.pip/cache/http%3A%2F%2Fpypi.python.org%2Fpackages%2Fsource%2Fv%2Fvirtualenv%2Fvirtualenv-1.8.4.tar.gz
      Running setup.py egg_info for package virtualenv

        warning: no previously-included files matching '*' found under directory 'docs/_templates'
        warning: no previously-included files matching '*' found under directory 'docs/_build'
    Installing collected packages: virtualenv
      Running setup.py install for virtualenv

        warning: no previously-included files matching '*' found under directory 'docs/_templates'
        warning: no previously-included files matching '*' found under directory 'docs/_build'
        Installing virtualenv script to /usr/local/share/python
        Installing virtualenv-2.7 script to /usr/local/share/python
    Successfully installed virtualenv
    Cleaning up...

Podemos verificar a correta instalação, listando os pacotes atualmente instalados:

    zemanel@victory ➜  ~  pip freeze
    distribute==0.6.32
    ipython==0.13.1
    numpy==1.6.2
    pyzmq==2.2.0.1
    stevedore==0.7.2
    tornado==2.4.1
    vboxapi==1.0
    virtualenv==1.8.4
    virtualenv-clone==0.2.4
    virtualenvwrapper==3.6
    wsgiref==0.1.2

Apartir deste momento, temos então acesso ao comando *virtualenv* (mais propriamente um *shell script*):

    zemanel@victory ➜  ~  which virtualenv
    /usr/local/share/python/virtualenv

Um ambiente virtual é meramente um diretório e podemos definir a sua localização, por ambiente, aquando da sua criação :

    # criação do ambiente virtual
    zemanel@victory ➜  ~  virtualenv instalacao_virtual_1
    New python executable in instalacao_virtual_1/bin/python
    Installing setuptools............done.
    Installing pip...............done.

    # conteúdo do diretório
    zemanel@victory ➜  ~  ls /Users/zemanel/Temp/instalacao_virtual_1
    bin
    include
    lib

    # verificação da versão do ambiente, que por omissão é a principal do sistema
    zemanel@victory ➜  ~  /Users/zemanel/Temp/instalacao_virtual_1/bin/python --version
    Python 2.7.3

Listando os pacotes instalados neste novo ambiente virtual, verificamos que é independente da instalação de sistema:

    zemanel@victory ➜  ~  /Users/zemanel/Temp/instalacao_virtual_1/bin/pip freeze
    wsgiref==0.1.2

Para, na linha de comandos, alternarmos para este novo ambiente, basta por exemplo *incluir* na sessão o conteúdo do seguinte *shell script*:

    zemanel@victory ➜  ~  source /Users/zemanel/Temp/instalacao_virtual_1/bin/activate
    (instalacao_virtual_1)zemanel@victory ➜  ~

O binário Python por omissão torna-se então o do ambiente virtual:

    (instalacao_virtual_1)zemanel@victory ➜  ~  which python
    /Users/zemanel/Temp/instalacao_virtual_1/bin/python

### virtualenvwrapper

    Conjunto de *shell scripts* que automatizam e adicionam inúmeras funcionalidades em redor do *virtualenv*, tais como:

    * Criação automática, por ambiente virtual, de *scripts* *pre* / *pós* ativação/desativação/remoção de um ambiente

    * ***TODO*** outros

    [http://pypi.python.org/pypi/virtualenvwrapper/](http://pypi.python.org/pypi/virtualenvwrapper/)

### ipython

Conhecido como uma consola de linha de comandos interativa com inúmeras funcionalidades acima da consola / interpretador de linha de comandos oficial, mas muito mais.

* Sítio oficial: [http://ipython.org](http://ipython.org)
* Documentação: [http://ipython.org/documentation.html](http://ipython.org/documentation.html)

Uma funcionalidade **fantástica** é o [modo *notebook*](http://ipython.org/ipython-doc/rel-0.13.1/interactive/htmlnotebook.html) através do qual se cria uma sessão Python interativa acessível pelo navegador de Internet, para edição de documentos ricos (intitulados *notebooks*) compostos por misto de blocos de texto e código-fonte executado *inline* no bloco em tempo-real, que possibilita inclusive a renderização de gráficos e imagens.

O sítio [http://nbviewer.ipython.org](http://nbviewer.ipython.org) agrega vários exemplos de documentos e suporta a pré-visualização de outros, fornecendo o seu endereço *online*.

Frameworks Web
--------------

### Django

*A framework web para perfeccionistas com prazos* e uma das mais conhecidas. A minha preferida.

* Sitio oficial: [http://www.djangoproject.com](http://www.djangoproject.com)

* Documentação: [http://www.djangoproject.com](http://www.djangoproject.com)

http://www.djangopackages.com

### Web2py

*Framework* de código aberto *full-stack* para desenvolvimento rápido de aplicações web orientadas a bases de dados rápidas, escaláveis, seguras e portáveis.

* Sitio oficial: [http://www.web2py.com](http://www.web2py.com)

* Documentação: [http://www.web2py.com/examples/default/documentation](http://www.web2py.com/examples/default/documentation)

* Livro: [http://www.web2py.com/book](http://www.web2py.com/book)

* Forum suporte: [http://groups.google.com/group/web2py/](http://groups.google.com/group/web2py/)

* Videos: [http://www.vimeo.com/search/videos/search:web2py/st/ceddf0b4/sort:newest/format:thumbnail](http://www.vimeo.com/search/videos/search:web2py/st/ceddf0b4/sort:newest/format:thumbnail)

### TornadoWeb

**TODO**

* Sitio oficial: [http://www.tornadoweb.org](http://www.tornadoweb.org)

* Documentação: [http://www.tornadoweb.org/documentation/index.html](http://www.tornadoweb.org/documentation/index.html)

### Google Webapp

**TODO**

* Sitio oficial e documentação da versão *1.x*, para Python 2.5: [https://developers.google.com/appengine/docs/python/tools/webapp/?hl=pt-PT](https://developers.google.com/appengine/docs/python/tools/webapp/?hl=pt-PT)

* Sitio oficial e documentação da versão *2.x*, para Python 2.7: [https://developers.google.com/appengine/docs/python/tools/webapp2?hl=pt-PT](https://developers.google.com/appengine/docs/python/tools/webapp2?hl=pt-PT)


### Zope

**TODO**

* Sitio oficial: [http://www.zope.org](http://www.zope.org)

* Documentação: [http://docs.zope.org](http://docs.zope.org)

### CherryPy

*Micro-framework* de código aberto.

* Sitio oficial: [http://www.cherrypy.org](http://www.cherrypy.org)

* Documentação: [http://docs.cherrypy.org/stable/index.html](http://docs.cherrypy.org/stable/index.html)

### Flask

http://flask.pocoo.org/


### Pyramid

Pyramid é uma framework de código aberto Python generalista, cujo objetivo principal é facilitar o desenvolvimento de aplicações *web* generalistas.

* Sitio oficial: [http://www.pylonsproject.org](http://www.pylonsproject.org)

* Documentação: [http://docs.pylonsproject.org/en/latest/](http://docs.pylonsproject.org/en/latest/)

















