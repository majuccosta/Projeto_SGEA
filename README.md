# SGEA

## Tema: Sistema de Gestão de Eventos Acadêmicos

O Sistema de Gestão de Eventos Acadêmicos (SGEA) é uma plataforma web desenvolvida para facilitar a organização e o gerenciamento de eventos promovidos por instituições de ensino. O projeto busca centralizar todas as etapas do processo, desde o cadastro dos eventos até a emissão automática de certificados, proporcionando uma solução eficiente para organizadores, participantes e administradores.

Em muitas instituições, o controle de inscrições, participantes e certificados ainda é realizado de forma manual ou utilizando diferentes ferramentas, o que dificulta a administração dos eventos e aumenta a possibilidade de erros. Diante desse cenário, o SGEA foi desenvolvido para automatizar essas atividades, oferecendo uma plataforma única, intuitiva e segura para toda a comunidade acadêmica.

O sistema foi construído utilizando o framework Django, adotando uma arquitetura organizada e escalável. Além do gerenciamento de eventos, a aplicação conta com autenticação de usuários, controle de permissões, upload de imagens, geração de certificados em PDF e painel administrativo para gerenciamento completo das informações.

## Tecnologias Utilizadas

O desenvolvimento do projeto utilizou tecnologias modernas para garantir desempenho, organização e facilidade de manutenção.

### Backend

* Python
* Django
* Django REST Framework
* SimpleJWT

### Frontend

* HTML5
* CSS3
* JavaScript
* Bootstrap 5
* Django Templates

### Banco de Dados

Durante o desenvolvimento foi utilizado o SQLite, sendo o PostgreSQL recomendado para ambientes de produção.

### Bibliotecas Auxiliares

* Pillow
* ReportLab
* Virtualenv

## Funcionalidades

O sistema contempla as principais funcionalidades necessárias para o gerenciamento de eventos acadêmicos.

### Gerenciamento de Eventos

Permite o cadastro, edição, exclusão e consulta de eventos, contendo informações como título, descrição, data, carga horária, limite de participantes e banner ilustrativo. Os eventos ficam disponíveis para visualização pública, possibilitando que os usuários conheçam seus detalhes antes da inscrição.

### Sistema de Inscrições

Usuários autenticados podem realizar inscrições nos eventos disponíveis. O sistema controla automaticamente o número de vagas, impedindo inscrições acima do limite estabelecido e evitando que um mesmo participante seja inscrito mais de uma vez no mesmo evento. Além disso, cada usuário possui uma área onde pode acompanhar todos os eventos nos quais está inscrito.

### Geração de Certificados

Após a participação no evento, o sistema possibilita a emissão automática de certificados em formato PDF. O documento é gerado dinamicamente contendo informações como nome do participante, nome do evento, carga horária e data de realização.

### Controle de Usuários

O sistema possui autenticação completa, incluindo cadastro, login e logout. Também foram implementados diferentes níveis de permissão para controlar o acesso às funcionalidades de acordo com o perfil de cada usuário.

### Painel Administrativo

A administração da plataforma é realizada por meio do Django Admin, permitindo o gerenciamento de usuários, eventos, inscrições, certificados e banners de maneira centralizada.

### API REST

Como complemento às funcionalidades da aplicação, o projeto possui suporte ao Django REST Framework com autenticação utilizando JSON Web Token (JWT), permitindo futuras integrações com aplicações web ou dispositivos móveis.

## Arquitetura do Projeto

O projeto está organizado em módulos independentes, facilitando sua manutenção e evolução.

A pasta **core** contém as configurações gerais da aplicação, incluindo arquivos responsáveis pelas configurações do Django, roteamento principal e inicialização do servidor.

A aplicação **accounts** concentra as funcionalidades relacionadas ao gerenciamento de usuários, autenticação e permissões.

A aplicação **events** reúne toda a lógica de negócio do sistema, incluindo modelos, formulários, rotas, templates e arquivos estáticos responsáveis pelo gerenciamento dos eventos.

A pasta **media** é utilizada para armazenar os banners enviados pelos administradores durante o cadastro dos eventos.

## Instalação

Para executar o projeto localmente, é necessário clonar o repositório, criar um ambiente virtual e instalar as dependências presentes no arquivo `requirements.txt`.

Após a instalação das dependências, devem ser executadas as migrações do banco de dados utilizando o comando:

```bash
python manage.py migrate
```

Em seguida, recomenda-se criar um superusuário para acesso ao painel administrativo:

```bash
python manage.py createsuperuser
```

Por fim, basta iniciar o servidor com:

```bash
python manage.py runserver
```

A aplicação estará disponível em:

```
http://127.0.0.1:8000/
```

## Auditoria

O sistema possui um módulo de auditoria responsável pelo registro das principais ações realizadas na plataforma, permitindo maior controle sobre alterações e operações executadas pelos usuários.

Após iniciar o servidor, os registros podem ser acessados por meio do endereço:

```
http://127.0.0.1:8000/logs/
```

## Considerações Finais

O SGEA demonstra como tecnologias modernas podem contribuir para a organização de eventos acadêmicos, reduzindo processos manuais e aumentando a eficiência administrativa. A integração entre gerenciamento de eventos, autenticação de usuários, controle de inscrições, emissão de certificados e painel administrativo torna a plataforma uma solução completa para instituições de ensino.

Além de atender às necessidades atuais, sua arquitetura permite futuras expansões, como integração com aplicativos móveis, envio automático de notificações, dashboards analíticos e novos módulos administrativos, tornando o sistema escalável e preparado para novas funcionalidades.
