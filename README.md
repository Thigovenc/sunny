# Sunny ☀️ — O Rei dos Orquestradores

![Go](https://img.shields.io/badge/Go-Backend-00ADD8?logo=go)
![Phoenix](https://img.shields.io/badge/Phoenix-LiveView-orange?logo=phoenixframework)
![Docker](https://img.shields.io/badge/Docker-Containers-blue?logo=docker)
![Status](https://img.shields.io/badge/status-em%20construção-yellow)

O **Sunny** é um ecossistema de orquestração de containers construído em arquitetura **monorepo**, combinando a eficiência de **Go** no plano de controle com a reatividade do **Phoenix Framework** para uma interface visual em tempo real.

Inspirado na resiliência do **Thousand Sunny**, o projeto foi desenhado para navegar pelos mares da infraestrutura distribuída, simplificando:

- Provisionamento de containers  
- Reconciliação de estado  
- Escalabilidade horizontal  
- Monitoramento em tempo real  
- Self-healing (roadmap)

> “Um navio capaz de atravessar qualquer mar — com a robustez da Adam Wood e a velocidade da concorrência de Go.”

---

# ⚓ Funcionalidades do Navio

## ⛵ Içar Velas (Provisionamento)

Gerencie o ciclo de vida dos containers:

- Criar workloads  
- Iniciar containers  
- Parar serviços  
- Remover workloads  
- Comunicação com Docker Engine

```bash
sunny deploy nginx
sunny stop nginx
sunny rm nginx
```

---

## 🌊 Expandir a Frota (Reconciliação)

Defina o estado desejado:

```yaml
service: api
replicas: 3
image: node:20
```

Sunny garante continuamente:

- 3 containers ativos  
- Recriação automática em caso de falha  
- Drift detection  
- Desired State vs Current State

---

## 🔭 Vigia (Dashboard Reativo)

Interface visual em Phoenix LiveView para:

- Containers ativos  
- Logs em streaming  
- Uso de CPU e memória  
- Eventos do cluster  
- Status de workloads

Inspirado em Docker Desktop, porém orientado a orquestração.

---

## 🪵 Casco de Adam Wood (Performance)

Combinação de dois runtimes resilientes:

### Go
- Goroutines  
- Channels  
- Baixa latência  
- Binários estáticos

### BEAM (Elixir)
- Supervisão nativa  
- Tolerância a falhas  
- Processos leves  
- Tempo real via LiveView

---

# 🛠 Stack Tecnológica

| Camada | Tecnologia | Papel |
|--------|------------|------|
| Control Plane | Go | Orquestração |
| Runtime | Docker Engine | Containers |
| API | REST / gRPC | Comunicação |
| Dashboard | Phoenix LiveView | Interface |
| Realtime | WebSockets | Eventos |
| Messaging (roadmap) | NATS | Event Bus |

---

# 📐 Arquitetura

```text
sunny/
├── core/                  # Sunny Engine (Go)
│   ├── scheduler/
│   ├── reconciler/
│   ├── container-runtime/
│   └── api/
│
├── dashboard/             # Vigia (Phoenix)
│   ├── live/
│   ├── components/
│   └── telemetry/
│
└── docs/
```

---

## Fluxo do Orquestrador

```text
Usuário
 ↓
CLI / Dashboard
 ↓
API (Sunny Core)
 ↓
Reconciler
 ↓
Docker Engine
 ↓
Estado Atual do Cluster
```

O reconciler compara continuamente:

```text
Desired State != Current State
→ Corrigir divergência
→ Recriar containers
→ Restaurar saúde do sistema
```

---

# 🚀 Como Embarcar

## Requisitos

- Go 1.22+
- Elixir + Phoenix
- Docker
- Make (opcional)

---

## 1. Suba o Sunny Engine

```bash
cd core

go mod tidy
go run main.go
```

---

## 2. Suba o Vigia

```bash
cd dashboard

mix deps.get
mix phx.server
```

---

## 3. Acesse o Dashboard

```bash
http://localhost:4000
```

Sua frota estará navegando.

---

# ⚙️ Comandos

```bash
sunny deploy redis
sunny scale redis --replicas=5
sunny logs redis
sunny status
sunny destroy redis
```

---

# 🧠 Princípios de Engenharia

Este projeto segue alguns princípios:

- Declarative over imperative  
- Reconciliation-driven architecture  
- Fault tolerance first  
- Event-driven design  
- Simplicidade operacional

Inspirado em conceitos de:

- Kubernetes  
- Nomad  
- Docker Swarm  
- Phoenix OTP Supervision

---

# 🗺 Roadmap

## Fase 1
- [ ] Provisionamento básico  
- [ ] Dashboard LiveView  
- [ ] Reconciliação simples  

## Fase 2
- [ ] Scheduler próprio  
- [ ] Service discovery  
- [ ] Health checks  

## Fase 3
- [ ] Self-healing  
- [ ] Rolling updates  
- [ ] Multi-node cluster  

---

# 🤝 Contribuindo

```bash
git clone https://github.com/seu-user/sunny.git
cd sunny
```

Abra issues, PRs ou ideias para fortalecer a frota.

---

## 🏴‍☠️ Filosofia do Projeto

Se Kubernetes é uma marinha inteira...

Sunny é um navio pirata rápido, resiliente e inteligente.

---

*"Rumo ao One Piece da Infraestrutura!"* ☀️