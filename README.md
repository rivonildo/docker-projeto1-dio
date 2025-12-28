

# 🚀 Projeto Docker + Apache | Desafio DIO.me

Este projeto foi desenvolvido como parte do **desafio prático da DIO.me**, com o objetivo de aplicar conceitos fundamentais de **Docker**, **Docker Compose**, **Apache (httpd)** e **desenvolvimento web com HTML, CSS e JavaScript**.

O foco foi criar um ambiente simples, funcional e totalmente reproduzível, utilizando **containers Docker**, seguindo boas práticas de versionamento com Git e GitHub.

---

## 🎯 Objetivo do Desafio

- Criar um servidor Apache utilizando Docker Compose  
- Executar uma aplicação web estática (HTML, CSS e JS) dentro de um container  
- Utilizar volumes para refletir alterações em tempo real  
- Versionar o projeto em um repositório GitHub  

---

## 🛠️ Tecnologias Utilizadas

- Docker
- Docker Compose
- Apache (httpd)
- HTML5
- CSS3
- JavaScript
- Git
- GitHub
- Linux (Ubuntu)

---

## 🧰 Ambiente Utilizado

- Sistema Operacional: **Ubuntu Linux**
- Terminal: **Bash**
- Editor de texto: **Nano**
- Docker Engine instalado localmente
- Docker Compose (plugin oficial)

---

## 📋 Pré-requisitos

Antes de iniciar, é necessário ter instalado:

- Docker
- Docker Compose
- Git
- Navegador Web

### 🔍 Verificação dos pré-requisitos

```bash
docker --version
docker compose version
git --version

### Estrutura do Projeto

docker-projeto1-dio/
├── compose.yml
├── README.md
└── website/
    ├── index.html
    ├── css/
    │   └── style.css
    ├── js/
    │   └── script.js
    └── images/

### ⚙️ Configuração do Docker Compose

Arquivo compose.yml utilizado no projeto:

services:
  apache:
    image: httpd:latest
    container_name: apache-dio
    ports:
      - "80:80"
    volumes:
      - ./website:/usr/local/apache2/htdocs

## 📌 Explicação da Configuração

- **image:** utiliza a imagem oficial do Apache (`httpd:latest`), garantindo estabilidade e compatibilidade.
- **ports:** expõe a porta **80** do container para a porta **80** da máquina host, permitindo acesso via navegador.
- **volumes:** mapeia o diretório local `website` para o diretório padrão do Apache (`/usr/local/apache2/htdocs`), possibilitando atualização em tempo real dos arquivos.

---

## 🧑‍💻 Desenvolvimento da Aplicação Web

### 📄 index.html
Página principal exibida pelo Apache, contendo HTML semântico e integração direta com os arquivos de **CSS** e **JavaScript**.

### 🎨 style.css
Responsável pela estilização da página, definição de cores, layout, tipografia e responsividade básica.

### ⚙️ script.js
Contém uma função JavaScript que exibe uma mensagem de confirmação ao clicar no botão, validando o funcionamento correto do container Apache com Docker Compose.

---

## ▶️ Comandos Executados no Projeto

### 📥 Clonar o repositório

```bash
git clone https://github.com/rivonildo/docker-projeto1-dio.git
cd docker-projeto1-dio

### Criar estrutura do site

mkdir -p website/css website/js website/images

### Criar e editar arquivos

nano website/index.html
nano website/css/style.css
nano website/js/script.js

### Subir o container

docker compose up -d

### Verificar containers em execução

docker ps

### Acesso à Aplicação
 
http://localhost 

### Resultado Esperado

Página carregando corretamente via Apache

Botão funcional exibindo mensagem de sucesso

Confirmação de que o Docker Compose está operando corretamente

### Comandos Úteis

### Parar o container

docker compose down

### Ver logs do Apache

docker logs apache-dio
