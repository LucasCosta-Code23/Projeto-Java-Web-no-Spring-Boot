# Projeto-Java-Web-no-Spring-Boot
Construindo uma API REST com banco de dados usando Java e Spring Boot - DevSuperior

# Tecnologias utilizadas
-  Spring Tool Suit (STS)
-  Postman

# Visão geral do sistema

Sistema que na verdade é uma API REST, um back end que disponibiliza os end points para você acessar via web de usuários e departamentos, com os seguintes casos de uso:
- Buscar todos usuários 
- Buscar um usuário pelo seu id
- Inserir um novo usuário

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/diagrama.png "Diagram.")

# EndPoints / Requisições

- Buscando todos os usuários

  
![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/endpointUsers.png "All users.")

  
![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/Users.png "All users.")

- Buscando um usuário por Id

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/Userbyid.png "One user per ID.")

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/User%20by%20id.png "One user per ID")

-  Salvar um novo usuário

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/SaveNewUser.png "Save new User")

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/new%20User.png "Save new User")

# Back end

![Image](https://github.com/LucasCosta-Code23/Projeto-Java-Web-no-Spring-Boot/blob/main/img/databaseH2Users.png "db H2 All users.")

#### Configuração do Maven Resources Plugin

```xml
<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>3.1.0</version>
</plugin>
```

#### Configurações do banco de dados

```
# Dados de conexão com o banco H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=

# Configuração do cliente web do banco H2
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Configuração para mostrar o SQL no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

#### Script SQL

```sql
INSERT INTO tb_department(name) VALUES ('Gestão');
INSERT INTO tb_department(name) VALUES ('Informática');

INSERT INTO tb_user(department_id, name, email) VALUES (1, 'Maria', 'maria@gmail.com');
INSERT INTO tb_user(department_id, name, email) VALUES (1, 'Bob', 'bob@gmail.com');
INSERT INTO tb_user(department_id, name, email) VALUES (2, 'Alex', 'alex@gmail.com');
INSERT INTO tb_user(department_id, name, email) VALUES (2, 'Ana', 'ana@gmail.com');
