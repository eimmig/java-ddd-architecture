# Codechella - Sistema de Vendas de Ingressos

## 📋 Sobre o Projeto

O **Codechella** é um sistema backend para gerenciamento de vendas de ingressos para eventos, desenvolvido com Java e Spring Boot, seguindo os princípios do **Domain-Driven Design (DDD)**. O projeto demonstra a implementação de uma arquitetura limpa e bem estruturada, separando claramente as responsabilidades entre as diferentes camadas da aplicação.

## 🏗️ Arquitetura DDD

Este projeto implementa o padrão Domain-Driven Design com a seguinte estrutura de camadas:

```
src/main/java/br/com/alura/codechella/vendas/
├── aplicacao/          # Camada de Aplicação (Application Layer)
│   ├── evento/         # Casos de uso e DTOs para eventos
│   ├── ingresso/       # Casos de uso e DTOs para ingressos
│   ├── usuario/        # Casos de uso e DTOs para usuários
│   └── venda/          # Casos de uso e DTOs para vendas
├── dominio/            # Camada de Domínio (Domain Layer)
│   ├── evento/         # Entidades e objetos de valor de eventos
│   ├── ingresso/       # Entidades e objetos de valor de ingressos
│   └── usuario/        # Entidades e objetos de valor de usuários
└── infra/              # Camada de Infraestrutura (Infrastructure Layer)
    ├── evento/         # Repositórios e persistência de eventos
    ├── ingresso/       # Repositórios e persistência de ingressos
    ├── usuario/        # Repositórios e persistência de usuários
    └── venda/          # Repositórios e persistência de vendas
```

### Camadas da Arquitetura

#### 🎯 **Camada de Domínio (Domain Layer)**
- Contém a lógica de negócio central
- Entidades: `Evento`, `Usuario`, `TipoIngresso`
- Objetos de Valor: `Endereco`, `Categoria`, `Setor`
- Independente de frameworks e tecnologias externas

#### 🔄 **Camada de Aplicação (Application Layer)**
- Orquestra os casos de uso do sistema
- Controllers REST: `EventoController`, `UsuarioController`, `VendaController`
- Services: `EventoService`, `UsuarioService`, `VendaService`
- DTOs para transferência de dados
- Tratamento de exceções e validações

#### 🛠️ **Camada de Infraestrutura (Infrastructure Layer)**
- Implementação de repositórios com JPA
- Persistência em banco de dados PostgreSQL
- Mapeamento objeto-relacional
- Comunicação com sistemas externos

## 🚀 Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.2.2**
- **Spring Web** - Para criação de APIs REST
- **Spring Data JPA** - Para persistência de dados
- **Spring Validation** - Para validação de dados
- **PostgreSQL** - Banco de dados relacional
- **Maven** - Gerenciamento de dependências e build

## 📦 Funcionalidades

### 🎪 **Gestão de Eventos**
- Cadastro de eventos com categoria, descrição, endereço e data
- Listagem de eventos disponíveis
- Associação de tipos de ingressos aos eventos

### 🎫 **Gestão de Ingressos**
- Criação de diferentes tipos de ingressos
- Definição de setores e preços
- Controle de disponibilidade

### 👥 **Gestão de Usuários**
- Cadastro de usuários com CPF, nome, data de nascimento e email
- Sistema de cupons de desconto

### 💰 **Sistema de Vendas**
- Processamento de vendas de ingressos
- Associação de vendas com usuários e eventos

## ⚙️ Configuração e Execução

### Pré-requisitos

- Java 17 ou superior
- Maven 3.6 ou superior
- PostgreSQL

### Configuração do Banco de Dados

1. Crie um banco de dados PostgreSQL chamado `codechella_db`
2. Configure as variáveis de ambiente:
   ```bash
   DB_HOST=localhost:5432
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   ```

### Executando a Aplicação

#### Usando Maven Wrapper (Recomendado)

```bash
# Windows
./mvnw.cmd spring-boot:run

# Linux/MacOS
./mvnw spring-boot:run
```

#### Usando Maven Local

```bash
mvn spring-boot:run
```

A aplicação estará disponível em: `http://localhost:8080`

### Executando os Testes

```bash
# Windows
./mvnw.cmd test

# Linux/MacOS
./mvnw test
```

## 📚 Endpoints da API

### Eventos
- `POST /eventos` - Cadastrar novo evento
- `GET /eventos` - Listar todos os eventos

### Usuários
- `POST /usuarios` - Cadastrar novo usuário

### Vendas
- `POST /vendas` - Processar nova venda

## 🏛️ Princípios DDD Aplicados

### **Linguagem Ubíqua**
O código utiliza termos do domínio de negócio como `Evento`, `Ingresso`, `Usuario`, `Venda`, `Categoria`, mantendo a linguagem consistente entre desenvolvedores e especialistas do domínio.

### **Agregados**
- **Evento**: Agregado principal que gerencia tipos de ingressos
- **Usuario**: Agregado para informações do usuário
- **Venda**: Agregado que relaciona usuário, evento e ingressos

### **Repositórios**
Interfaces de repositório definem contratos para persistência, mantendo a camada de domínio independente da infraestrutura.

### **Serviços de Aplicação**
Orquestram os casos de uso, coordenando interações entre agregados e repositórios.

## 🤝 Contribuição

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Crie um Pull Request

## 📄 Licença

Este projeto é um exemplo educacional desenvolvido para demonstrar a implementação de arquitetura DDD com Spring Boot.

## 📧 Contato

Para dúvidas ou sugestões sobre o projeto, entre em contato através do repositório no GitHub.

---

**Codechella** - Demonstrando Domain-Driven Design na prática com Java e Spring Boot 🎵
