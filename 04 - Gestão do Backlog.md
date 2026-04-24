# 📘 Gestão de Backlog no Scrum — Modelo Detalhado de Cartão

A qualidade do **Product Backlog** impacta diretamente a previsibilidade, a organização e a qualidade das entregas no **Scrum**.  
Um item mal descrito gera dúvidas, retrabalho e desalinhamento. Já um cartão bem estruturado melhora a comunicação, facilita estimativas e reduz riscos.

Abaixo está um modelo **mais detalhado** para estruturar itens de backlog com maior clareza e maturidade técnica.

---

# 🧾 Estrutura Completa de um Cartão de Backlog

## 🔹 1. Informações Gerais

### 🆔 ID
Identificador único do item (ex: US-023, BUG-014).  
Permite rastreabilidade, histórico de mudanças e referência cruzada com commits e testes.

### 🏷 Título
Descrição curta e objetiva do que será desenvolvido.  
Deve ser claro o suficiente para identificar o propósito do item sem precisar ler a descrição completa.

### 📝 Descrição Detalhada
Explicação clara do problema ou necessidade.  
Deve contextualizar:
- Qual é o problema?
- Para quem?
- Por que isso é importante?
- Qual impacto esperado no produto?

Evitar descrições vagas como: "Ajustar tela".  
Preferir: "Ajustar layout da tela de login para melhorar responsividade em dispositivos móveis".

### 📂 Tipo
Classificação do item:
- História de Usuário
- Bug
- Melhoria
- Requisito Técnico
- Épico

Essa classificação ajuda na organização e na análise de métricas.

### 👤 Responsável
Pessoa que está conduzindo tecnicamente a execução.  
Não significa trabalho individual, mas sim referência principal para dúvidas.

### 🎯 Product Owner Responsável
Responsável pela priorização e validação do item.

### 📌 Status
- Backlog
- Refinamento
- Pronto para Sprint
- Em Desenvolvimento
- Em Teste
- Concluído

### 🔖 Etiquetas (Labels)
Facilitam filtros e organização:
- Front-end
- Back-end
- API
- Mobile
- Segurança
- Performance
- Banco de Dados

### ⚖ Prioridade
Pode usar:
- Alta / Média / Baixa  
ou  
- MoSCoW (Must, Should, Could, Won’t)

---

# 🔹 2. User Story

A história descreve valor sob a perspectiva do usuário.

### Estrutura recomendada

> Como **[tipo de usuário]**  
> Quero **[ação ou funcionalidade]**  
> Para **[benefício ou resultado esperado]**

### Exemplo detalhado

> Como cliente autenticado  
> Quero redefinir minha senha  
> Para recuperar o acesso à minha conta de forma segura sem precisar entrar em contato com suporte.

Uma boa User Story:
- Foca no valor
- Não descreve solução técnica
- É compreensível para stakeholders

---

# 🔹 3. Critérios de Aceite

São condições objetivas que determinam quando a história pode ser considerada válida.

Devem ser:
- Claros
- Testáveis
- Mensuráveis
- Sem ambiguidade

### Exemplo

- O usuário deve informar um e-mail válido cadastrado no sistema.
- O sistema deve enviar e-mail em até 1 minuto.
- O link de redefinição deve expirar em 24 horas.
- A nova senha deve conter no mínimo 8 caracteres, 1 número e 1 caractere especial.
- O sistema deve registrar log da operação.

Critérios bem definidos reduzem discussões futuras.

---

# 🔹 4. Casos de Uso

Detalham o fluxo funcional da funcionalidade.

### Estrutura

**Nome:** Recuperação de Senha  
**Ator:** Usuário  
**Objetivo:** Permitir redefinição de senha  
**Pré-condições:**  
- Usuário deve estar cadastrado

### Fluxo Principal
1. Usuário acessa tela de login
2. Clica em "Esqueci minha senha"
3. Informa e-mail
4. Sistema valida cadastro
5. Sistema envia link
6. Usuário redefine senha

### Fluxos Alternativos
- E-mail inválido → Exibir mensagem clara
- Link expirado → Solicitar novo envio

---

# 🔹 5. Casos de Teste

Garantem validação funcional e técnica.

### Exemplo de tabela

| ID | Cenário | Entrada | Resultado Esperado |
|----|----------|----------|-------------------|
| CT01 | E-mail válido | usuario@email.com | Link enviado |
| CT02 | E-mail inexistente | teste@email.com | Mensagem informativa |
| CT03 | Senha fraca | 123456 | Bloqueio e aviso |

Podem incluir:
- Testes unitários
- Testes de integração
- Testes automatizados
- Testes de regressão

---

# 🔹 6. Definition of Done (DoD)

Define quando o item está realmente concluído.

Exemplo:

- Código desenvolvido
- Testes unitários criados
- Cobertura mínima de testes atingida
- Code review aprovado
- Deploy em ambiente de homologação
- Validação do Product Owner
- Documentação atualizada

Sem DoD clara, o conceito de “pronto” varia entre membros.

---

# 🔹 7. Estimativa

Serve para planejamento, não para cobrança individual.

### Técnicas comuns

- Story Points (Fibonacci: 1, 2, 3, 5, 8, 13...)
- T-Shirt Size (P, M, G)
- Estimativa em horas (quando aplicável)

Estimativa é responsabilidade dos Developers.

---

# 🔹 8. Dependências

Registrar dependências evita bloqueios:

- Depende de API externa?
- Depende de outra história?
- Depende de decisão de negócio?
- Depende de fornecedor?

---

# 🔹 9. Riscos

Mapear riscos aumenta previsibilidade:

- Complexidade técnica desconhecida
- Mudança regulatória
- Integração com sistema legado
- Performance crítica

---

# 🔹 10. Anexos e Evidências

- Protótipos
- Diagramas
- Regras de negócio
- Documentos técnicos
- Prints de erro (em caso de bug)

---

# 🧠 Checklist de Qualidade (Pré-Sprint)

✔ Está clara e compreensível?  
✔ Possui critérios de aceite testáveis?  
✔ Está pequena o suficiente para uma sprint?  
✔ Está estimada?  
✔ Possui responsável?  
✔ Tem dependências mapeadas?  
✔ Possui DoD definida?  

---

# 🎯 Benefícios de um Cartão Bem Estruturado

- Redução de retrabalho  
- Maior clareza entre negócio e tecnologia  
- Melhor estimativa  
- Menor risco técnico  
- Aumento da qualidade  
- Maior previsibilidade da Sprint  

---

# 💡 Conclusão

Um bom cartão de backlog não é excesso de documentação, mas sim **organização inteligente da informação**.

Quanto mais claro o item, menor a incerteza.  
Quanto menor a incerteza, maior a eficiência do time.