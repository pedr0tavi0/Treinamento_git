
---

# 📄 Documentação de Estrutura SCM

## 📂 Nomenclatura de Branches

Para manter a organização e facilitar o rastreamento de tarefas, utilizamos a seguinte convenção para nomear nossas branches:

```
<tipo>/<id_jira>-<descricao>
```

### Tipos de Branches

- **feature**: Para novas funcionalidades.
- **bugfix**: Para correções de bugs.
- **hotfix**: Para correções urgentes em produção.
- **refactor**: Para alterações de código sem alteração do funcionamento.

### Exemplos

- `feature/JIRA-123-adicionar-autenticacao`
- `bugfix/JIRA-456-corrigir-login`
- `hotfix/JIRA-789-corrigir-erro-404`

---

## 📝 Nomenclatura de Commits

Os commits devem seguir esta convenção para melhorar a clareza e o rastreamento:

```
git add .
git commit -m "<tipo>(<id_jira>): <descricao>"
```

### Tipos de Commits

- **feat**: Nova funcionalidade.
- **fix**: Correção de um bug.
- **docs**: Alterações na documentação.
- **style**: Mudanças que não afetam a lógica do código (formatação, espaçamento, etc.).
- **refactor**: Alterações na estrutura do código que não adicionam funcionalidades nem corrigem bugs.

### Exemplos

- `feat(JIRA-123): Criar botão de cadastro de usuário`
- `fix(JIRA-456): Corrigir erro de validação no formulário`
- `docs(JIRA-789): Atualizar documentação da API`

---

## ✅ Boas Práticas

- **Consistência**: Mantenha a consistência na nomenclatura para facilitar a colaboração entre a equipe.
- **Clareza**: Use descrições claras e concisas para que outros membros da equipe possam entender rapidamente o propósito da branch ou do commit.
- **Referência ao Jira**: Sempre inclua o ID do Jira para rastreamento eficiente das tarefas relacionadas.
- **Limite de Comprimento**: 
  - Mantenha a linha de resumo dos commits com até 72 caracteres;
  - Use uma linha em branco para separá-la da descrição detalhada, se necessário.

---

# 🔄 Processo de SCM


## 🚀 Passo a Passo do Processo de SCM

### 1. Criação da Branch

- **Tarefa no Jira**: Alinhe-se a uma tarefa do Jira conforme discutido nas reuniões de planejamento e daily.
- **Criação da Branch**: 
  ```bash
  git checkout develop
  git pull origin develop
  git checkout -b feature/NGEN-615-listagem-de-usuarios
  ```
- **Atualização do repositório remoto**: 
  ```bash
  git push -u origin --set-upstream feature/NGEN-615-listagem-de-usuarios // Apenas deve ser dado na primeira vez , quando a branch não estiver criada no repositorio remoto(GITHUB)
  ```

---

### 2. Desenvolvimento

- O desenvolvedor implementa o endpoint da API para a listagem de usuários na branch criada.
- Realiza commits frequentes com mensagens claras:
  ```bash
  git add .
  git commit -m "feature(NGEN-1597): Criação do endpoint para listagem de usuários"
  ```

---

### 3. Revisão do Código

- Antes de concluir o desenvolvimento, atualize a sua branch em relação à develop:
  ```bash
  git checkout develop
  git pull origin develop
  git checkout feature/NGEN-615-listagem-de-usuarios
  git merge develop
  ```
- Após concluir o desenvolvimento:
  ```bash
  git push origin feature/NGEN-615-listagem-de-usuarios
  ```
- Abra um **Pull Request** para revisão de código.

---

### 4. Mesclagem

- Após a aprovação da revisão:
  ```bash
  git checkout develop
  git merge feature/NGEN-615-listagem-de-usuarios
  git push origin develop
  ```

---

### 5. Testes

- Execute testes automatizados (dependendo da configuração) e verifique se o endpoint está funcionando corretamente.
- Se necessário, faça ajustes e repita os passos de commit e push.

---

### 7. Documentação

- Atualize a documentação do projeto, incluindo detalhes sobre o novo endpoint, como usá-lo e exemplos de resposta.

---

### 8. Monitoramento

- Após a implantação em produção, monitore o comportamento do sistema.
- Não há comandos Git específicos nesta etapa, mas é importante acompanhar logs e feedbacks.

---

## 🔖 Dentro da branch mãe criar uma branch task

*(Exemplo de branch task não fornecido — incluir conforme necessidade.)*

---

# 🗨️ Padronização dos Comentários em Card de Tarefas

Para mantermos uma comunicação clara, objetiva e uniforme no Jira, os comentários em cards devem seguir o seguinte modelo (utilizando **Markdown**):

---

## Exemplo

**Tela de Listagem Feedbacks implementada:**

- Criada a página de listagem de feedbacks;
- Adicionado novo componente de card de feedback;
- Atualizado o service de feedbacks com nova rota da API;
- Criada nova enumeração para status de feedback.

---

## 🎯 Dicas Gerais

- Utilize **negrito** para títulos ou partes importantes;
- Mantenha o tempo verbal consistente (preferência pelo passado, indicando que foi implementado);
- Evite parágrafos longos — seja direto e prático;
- Caso necessário, use emojis para destacar status 📌 ou alertas ⚠️, com moderação.

---
