# 🖥️ Sistema de Chamados de TI

Aplicação web em **Spring Boot** para gerenciamento de chamados de TI, com autenticação de usuários, painel administrativo, dashboard com estatísticas e exportação de relatórios em PDF/Excel.

---

## 🚀 Tecnologias utilizadas
- Java 17
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Spring Security
- Thymeleaf
- MySQL
- iText (PDF)
- Apache POI (Excel)
- Spring Mail (envio de emails)
- Chart.js (gráficos no dashboard)

---

## ⚙️ Configuração do ambiente

### Pré-requisitos
- Java 17+
- Maven
- MySQL
- IDE (IntelliJ, Eclipse ou VS Code)

### Banco de dados
Crie o banco de dados:
```sql
CREATE DATABASE chamadosdb;

Configure o arquivo src/main/resources/application.properties:

spring.datasource.url=jdbc:mysql://localhost:3306/chamadosdb
spring.datasource.username=root
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=seu_email@gmail.com
spring.mail.password=sua_senha_app
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true


▶️ Executando o projeto

No terminal:
mvn spring-boot:run

Acesse:

http://localhost:8080/login (localhost in Bing) → Login
http://localhost:8080/register (localhost in Bing) → Cadastro de usuários
http://localhost:8080/chamados (localhost in Bing) → Chamados (usuário autenticado)
http://localhost:8080/admin/chamados (localhost in Bing) → Gerenciamento de chamados (admin)
http://localhost:8080/admin/dashboard (localhost in Bing) → Dashboard com estatísticas

👥 Perfis de usuário

ROLE_USER → abre e acompanha chamados.
ROLE_ADMIN → gerencia chamados, acessa dashboard e exporta relatórios.

📊 Funcionalidades

Cadastro e login de usuários.
Abertura e listagem de chamados.
Painel administrativo para fechar chamados.
Dashboard com estatísticas e gráficos (Chart.js).
Exportação de relatórios em PDF e Excel.
Envio de relatórios por email.
Agendamento automático de envio diário de relatórios.

Estrutura do projeto

src/main/java/com/empresa/chamados
├── entity
│   ├── Usuario.java
│   └── Chamado.java
├── repository
│   ├── UsuarioRepository.java
│   └── ChamadoRepository.java
├── service
│   ├── ChamadoService.java
│   └── RelatorioEmailService.java
├── controller
│   ├── UsuarioController.java
│   ├── ChamadoController.java
│   ├── AdminChamadoController.java
│   ├── AdminDashboardController.java
│   └── RelatorioController.java
└── security
    ├── SecurityConfig.java
    ├── UserDetailsImpl.java
    └── UserDetailsServiceImpl.java


📧 Envio automático de relatórios
O sistema envia relatórios em PDF diariamente às 8h para o email configurado no RelatorioScheduler.

📝 Licença
Este projeto é livre para uso e modificação.

✅ Passo a passo para instalar o Maven no Windows
1. Baixar o Maven
Acesse: https://maven.apache.org/download.cgi (maven.apache.org in Bing)
Baixe a versão binária ZIP (ex: apache-maven-3.9.6-bin.zip)

2. Extrair e mover
Extraia o ZIP para uma pasta permanente, ex:
C:\Program Files\Apache\Maven

3. Configurar variáveis de ambiente
Abra o menu Iniciar → digite “variáveis de ambiente”
Clique em Variáveis de Ambiente
Em “Variáveis do sistema”:
Adicione uma nova variável:
Nome: MAVEN_HOME
Valor: C:\Program Files\Apache\Maven
Edite a variável Path e adicione:
C:\Program Files\Apache\Maven\bin

4. Testar no terminal
Feche e reabra o PowerShell ou CMD
Digite: mvn -v
Se aparecer a versão do Maven e do Java, está tudo certo!

🧪 Exemplo de saída esperada
Apache Maven 3.9.6
Java version: 17.0.10, vendor: Oracle Corporation

Depois disso, volte para sua pasta do projeto e rode:
mvn clean install

Isso vai baixar todas as dependências e resolver os erros de importação na sua IDE.

