# 🧠 Guia Prático de Arquitetura de Software

Um checklist + modelo mental para arquitetar seus próprios projetos de forma consciente, usando princípios sólidos, padrões de design e pensamento estratégico.

---

## 🔰 Etapa 1: Entendimento do Problema

- [ ] Qual problema real estou resolvendo?
- [ ] Quem vai usar? Como?
- [ ] Qual é o núcleo do sistema (domínio principal)?
- [ ] O que é essencial agora (MVP)? O que pode ficar pra depois?

**Mentalidades aplicadas:**  
Lean Thinking, MVP, Product Thinking

---

## 🧱 Etapa 2: Modelagem de Domínio

- [ ] Qual a linguagem onipresente entre time, negócio e código?
- [ ] Quais são as entidades e seus comportamentos?
- [ ] O que muda com frequência?
- [ ] Onde há regras de negócio mais críticas?

**Conceitos úteis:**  
- DDD (Domain-Driven Design)  
- Entity, Value Object, Aggregate, Service

**Padrões recomendados:**  
Strategy, Template Method, State

---

## 🔄 Etapa 3: Modelagem de Fluxos

- [ ] Quais são os principais fluxos do sistema (ex: do clique ao banco)?
- [ ] O que acontece antes, durante e depois de cada ação?
- [ ] Quais eventos o sistema gera ou consome?

**Ferramentas úteis:**  
Event Storming, User Story Mapping, Diagramas de Sequência

**Padrões recomendados:**  
Command, Handler, Event Bus, Observer, Mediator

---

## 🧰 Etapa 4: Escolha de Arquitetura

- [ ] Preciso desacoplar domínio da infraestrutura?
- [ ] As regras de negócio precisam viver isoladas de detalhes técnicos?

**Sugestões:**

| Situação | Arquitetura Ideal |
|---------|------------------|
| Sistema simples, rápido | MVC ou Monolito Modular |
| Domínio central forte | Clean, Hexagonal, Onion |
| Escalabilidade independente | Microserviços |
| Reativo / integrações | Event-Driven Architecture |

**Princípios aplicados:**  
SOLID, Dependency Inversion

---

## 🧱 Etapa 5: Componentização do Código

- [ ] O sistema está dividido por responsabilidade?
- [ ] Consigo entender o que cada módulo faz em 5 minutos?
- [ ] As dependências seguem da periferia para o centro?

**Padrões úteis:**  
Service Layer, Repository, Adapter, Decorator, Factory, Builder

---

## ⚙️ Etapa 6: Comunicação & Infraestrutura

- [ ] Como os módulos se comunicam? (sincrono/assíncrono?)
- [ ] Há pontos de falha previsíveis?
- [ ] Preciso de filas, eventos ou APIs externas?

**Padrões úteis:**  
Proxy, Circuit Breaker, Retry, Timeout, Observer, EventBus, CQRS

---

## 🛡️ Etapa 7: Testes, Segurança e Resiliência

- [ ] O que acontece se algo falhar?
- [ ] Existem testes automatizados para os fluxos principais?
- [ ] É possível atualizar uma parte sem quebrar o todo?

**Práticas e padrões:**  
Decorator (para logging, auth, cache),  
Factory (para facilitar mocks),  
Dependency Injection

---

## 📚 Etapa 8: Documentação e Evolução

- [ ] Estou documentando as decisões arquiteturais?
- [ ] Novas pessoas conseguem entender a estrutura?
- [ ] É fácil alterar e testar partes isoladas?

**Ferramentas úteis:**  
- C4 Model  
- Architecture Decision Records (ADR)  
- README’s por módulo/pasta

---

## 🔁 Fluxo de Decisão

1. **Qual o problema a ser resolvido?**
2. **Mapeie os fluxos e o domínio**
3. **O domínio precisa ser isolado da infraestrutura?**
   - **Sim:** use uma arquitetura **Clean**, **Hexagonal** ou **Onion**
   - **Não:** use **MVC** ou um **Monolito Modular**
4. **Componentize por responsabilidade**
5. **Defina a comunicação entre módulos**
   - REST
   - Eventos
   - Fila
   - Mensageria etc.
6. **Aplique padrões de design conforme os problemas surgirem**
7. **Garanta:**
   - Testes automatizados
   - Resiliência a falhas
   - Documentação leve e acessível
   - 
---

## 🧠 Padrões de Design por Tipo de Problema

| Problema                         | Padrão de Design            |
|----------------------------------|-----------------------------|
| Criação de objetos               | Factory, Builder, Singleton |
| Separar lógica de apresentação  | MVC, MVP, MVVM              |
| Variar comportamento em runtime | Strategy, State             |
| Compartilhar instância comum    | Singleton, Flyweight        |
| Encapsular comandos             | Command                     |
| Estender sem modificar          | Decorator, Adapter, Proxy   |
| Reagir a eventos                | Observer, Mediator          |

---

**Dica final:**  
> Não pense “qual padrão aplicar?”, pense:  
> **“Qual problema estou enfrentando?”**  
> — A escolha do padrão vem como consequência.

