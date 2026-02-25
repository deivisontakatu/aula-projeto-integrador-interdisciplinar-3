# 1.Visão Arquitetural

A primeira entrega deve consolidar **a arquitetura global do sistema**, garantindo:

- Definição clara das camadas
- Separação de responsabilidades
- Padrão de comunicação entre módulos
- Estratégia de integração vertical e horizontal
- Base técnica sólida para o MVP

> Esta etapa é estrutural.  
> Não é sobre implementar — é sobre projetar corretamente.

---

# 2. 🏗 Princípios Arquiteturais do Projeto

A arquitetura deve seguir os seguintes princípios:

## 🔹 2.1 Arquitetura em Camadas
Separação clara entre:
- Coleta de dados
- Comunicação
- Processamento
- Persistência
- Apresentação

## 🔹 2.2 Baixo Acoplamento
Cada módulo deve operar de forma independente, comunicando-se via API ou protocolo padronizado.

## 🔹 2.3 Alta Coesão
Cada camada deve ter uma única responsabilidade bem definida.

## 🔹 2.4 Escalabilidade
A arquitetura deve permitir:
- Aumento de sensores
- Aumento de usuários mobile
- Crescimento do volume de dados

## 🔹 2.5 Interoperabilidade
Uso de padrões abertos:
- MQTT para mensageria
- JSON como estrutura de dados
- API REST para integração

---

# 3. 🌐 Visão Macro da Arquitetura

Fluxo estrutural do sistema:

Dispositivos IoT  
↓  
Broker MQTT  
↓  
Backend / API  
↓  
Banco de Dados  
↓  
Camada Cloud  
↓  
Aplicativo Mobile  
↓  
Interface Industrial  

---

# 4. 🧱 Camadas Arquiteturais Detalhadas

---

## 🔹 4.1 Camada de Dispositivos (IoT)

### Responsabilidade:
- Coleta de dados físicos
- Conversão para formato digital
- Publicação via MQTT

### Decisões arquiteturais:
- Definir estrutura de tópicos MQTT
- Definir frequência de envio
- Definir padrão de payload

Exemplo de payload:

```json
{
  "deviceId": "sensor01",
  "timestamp": "2026-03-10T14:32:00Z",
  "temperature": 78.5
}
```

## 🔹 4.2 Camada de Comunicação (MQTT)

### Responsabilidade:
- Gerenciar mensagens
- Garantir entrega
- Organizar tópicos

### Definições necessárias:
- Padrão de nomenclatura de tópicos (Exemplo: `industria/linha1/maquinaA/temperatura`)
- Definir QoS
- Definir política de retenção

## 🔹 4.3 Camada de Processamento (Backend)

### Responsabilidade:
- Receber mensagens do broker
- Validar dados
- Aplicar regras de negócio
- Persistir dados
- Expor API REST

### Componentes:
- Controller (entrada)
- Service (regra de negócio)
- Repository (persistência)

### Endpoints esperados:
- `POST /dados`
- `GET /dados`
- `GET /alertas`

## 🔹 4.4 Camada de Persistência

### Responsabilidade:
- Armazenamento estruturado
- Histórico de dados
- Suporte a consultas analíticas

### Decisões:
- Banco relacional ou NoSQL
- Estratégia de indexação
- Política de retenção histórica

## 🔹 4.5 Camada Cloud

### Responsabilidade:
- Hospedagem da API
- Escalabilidade
- Segurança
- Backup

### Definições:
- Ambiente de deploy
- Estratégia de versionamento
- Controle de acesso

## 🔹 4.6 Camada de Aplicação (Mobile)

### Responsabilidade:
- Consumo da API
- Visualização de dados
- Notificações
- Interação do usuário

### Definições:
- Arquitetura do app (MVC, MVVM, etc.)
- Gerenciamento de estado
- Estratégia de autenticação

## 🔹 4.7 Camada de Interface Industrial

### Responsabilidade:
- Visualização operacional
- Dashboards em tempo real
- Indicadores de desempenho
- Alertas visuais

### Elementos obrigatórios:
- KPIs industriais
- Indicadores de tendência
- Estados críticos
- Hierarquia visual clara

---

# 5. 🔄 Arquitetura da Integração

## 🔹 5.1 Integração Vertical (Fluxo de Dados)

Operação → Supervisão → Gestão → Decisão

A arquitetura deve demonstrar:
- Como o dado bruto vira informação
- Como a informação vira indicador
- Como o indicador apoia decisão

## 🔹 5.2 Integração Horizontal (Entre Áreas)

A API deve permitir integração futura com:
- Produção
- Manutenção
- Logística
- TI

A arquitetura precisa prever:
- Padrão de integração
- Escalabilidade
- Documentação de endpoints

---

# 6. 📐 Modelo Arquitetural Recomendado

Utilizar combinação de:
- Arquitetura em Camadas
- Arquitetura Orientada a Serviços
- Event-Driven Architecture (via MQTT)

O sistema é híbrido:
- Comunicação assíncrona (MQTT)
- Comunicação síncrona (REST)

---

# 7. 🔐 Arquitetura de Segurança

Definir:
- Autenticação na API
- Autorização por perfil
- Criptografia de dados
- Proteção do broker MQTT
- Controle de acesso no mobile

---

# 8. 📊 Requisitos Não Funcionais

A arquitetura deve contemplar:
- Disponibilidade
- Escalabilidade
- Performance
- Confiabilidade
- Manutenibilidade

---

# 9. 📋 Artefatos Arquiteturais Obrigatórios

A Entrega 1 deve conter:
- Diagrama geral da arquitetura
- Diagrama de fluxo de dados
- Diagrama de camadas
- Modelo de dados inicial
- Estrutura de tópicos MQTT
- Estrutura da API
- Mapa de integração vertical e horizontal