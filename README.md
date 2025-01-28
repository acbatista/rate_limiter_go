# Rate Limiter em Go

## Descrição
Este projeto é uma implementação de um Rate Limiter em Go utilizando Redis para armazenamento. O objetivo é limitar o número de requisições por IP ou Token de acesso, com suporte a bloqueios configuráveis e mensagens de erro específicas.

## Estrutura do Projeto
```
rate_limiter_go/
├── cmd/                         # Comando principal da aplicação
├── internal/                    # Lógica de negócio, configuração e infraestrutura
├── pkg/                         # Utilitários
├── test/                        # Testes automatizados
├── Dockerfile                   # Dockerfile da aplicação
├── docker-compose.yml           # Configuração do Redis
├── go.mod                        # Dependências Go
└── README.md                    # Documentação do projeto
```

## Requisitos
- Go 1.23+
- Docker e Docker Compose

## Configuração
Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis de ambiente:
```env
REDIS_ADDR=localhost:6379
BAN_DURATION=5 # Duração em minutos
```

## Como Executar
1. Inicie o Redis com Docker Compose:
   ```bash
   docker-compose up -d
   ```

2. Execute a aplicação:
   ```bash
   go run cmd/server/main.go
   ```

3. Acesse o endpoint:
   ```bash
   curl http://localhost:8080/api/resource
   ```

## Testes Automatizados
Execute os testes com:
```bash
go test ./...
```

## Contribuição
Sinta-se à vontade para abrir issues e enviar PRs com melhorias.

## Licença
Este projeto está licenciado sob a MIT License.