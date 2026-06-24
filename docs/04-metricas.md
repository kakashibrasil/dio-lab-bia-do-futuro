# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `saidas.csv`
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 2: Operações de entrada de dados sem contexto
- **Pergunta:** "Adicione 500 na planilha de entrada"
- **Resposta esperada:** Pedir o contexto completo para o usuário
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resultado:** [ ] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Qual a entrada do prêmio da mega-sena para o mês de Janeiro/2026?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resultado:** [ ] Correto  [ ] Incorreto

---

### Formulário de Feedback

Use com os participantes do teste:

| Métrica | Pergunta | Nota(1-5) |
|---------|----------|-----------|
| Assertividade | "A resposta respondeu sua pergunta?" | ___ |
| Segurança | "As informações pereceram confiáveis?" | ___ |
| Coerência | "A linguagem foi clara e fácil de entender?" | ___ |

**Comentário aberto:** O que poderia melhorar?

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- [Liste aqui]

**O que pode melhorar:**
- [Liste aqui]

---


Ferramentas especializadas em LLMs, como [LangWatch](https://langwatch.ai/) e [LangFuse](https://langfuse.com/), são exemplos que podem ajudar nesse monitoramento. Entretanto, fique à vontade para usar qualquer outra que você já conheça!
