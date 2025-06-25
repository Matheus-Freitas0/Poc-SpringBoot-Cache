# 📦 Projeto Spring Boot com Cache Redis

Este projeto é uma prova de conceito (PoC) simples demonstrando o uso de cache com Redis no Spring Boot. Ele simula uma busca por produtos e aplica cache para otimizar as chamadas subsequentes.

## 🚀 Tecnologias Utilizadas

- Java 21
- Spring Boot 3.5.3
  - Spring Cache
  - Spring Data Redis
- Redis
- Maven

## 💡 Funcionalidade

A aplicação simula uma API de produtos que utiliza cache para evitar múltiplas chamadas ao mesmo dado. O cache é configurado usando Redis e a anotação `@Cacheable`.

### Exemplo de execução:
```bash
Id: 1: Buscando produtos... -> Produto retornado
Id: 2: Buscando produtos... -> Produto retornado
Id: 1: (usando cache)
Id: 1: (usando cache)
Id: 1: (usando cache)
```

## 🛠️ Como Executar Localmente

### Pré-requisitos

- Java 21+
- Maven 3.8+
- Redis em execução local (porta padrão `6379`)

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/Cache.git
   cd Cache
   ```

2. Execute o Redis localmente (via Docker, por exemplo):
   ```bash
   docker run --name redis -p 6379:6379 redis
   ```

3. Execute a aplicação:
   ```bash
   ./mvnw spring-boot:run
   ```

## 🔁 Cache com Redis

O método `getById` da classe `ProductService` está anotado com `@Cacheable("products")`. O Spring irá armazenar o retorno da chamada no Redis, evitando o custo da operação simulada de latência nas próximas chamadas com o mesmo `id`.

```java
@Cacheable("products")
public Product getById(Long id) { ... }
```

## 🧪 Testes

A dependência de testes já está incluída no projeto. Para rodar os testes (quando adicionados):
```bash
./mvnw test
```

## 🧑‍💻 Autor

Matheus M. Freitas  
Desenvolvedor Full Stack | Java & Spring | React  
[LinkedIn](https://www.linkedin.com/in/matheus-m-freitas/)

---
