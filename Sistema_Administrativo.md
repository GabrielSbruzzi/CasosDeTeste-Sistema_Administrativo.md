# Casos de Teste - Sistema Administrativo

**Ambiente:** Web, Navegador Chrome

**Autor:** Gabriel Sbruzzi

Este arquivo contém a documentação detalhada dos casos de teste aplicados ao projeto de sistema administrativo.

## Índice
- [Cenário de Teste 1 - Login com Dados Inválidos](#cenário-de-teste-1---login-com-dados-inválidos)
- [Cenário de Teste 2 - Cadastro de Novo Usuário com Dados Incompletos](#cenário-de-teste-2---cadastro-de-novo-usuário-com-dados-incompletos)
- [Cenário de Teste 3 - Cadastro de Novo Usuário com Dados Válidos](#cenário-de-teste-3---cadastro-de-novo-usuário-com-dados-válidos)
- [Cenário de Teste 4 - Edição de Usuário com Dados Inválidos](#cenário-de-teste-4---edição-de-usuário-com-dados-inválidos)
- [Cenário de Teste 5 - Exclusão de Usuário](#cenário-de-teste-5---exclusão-de-usuário)
- [Cenário de Teste 6 - Acesso a Relatórios com Sucesso](#cenário-de-teste-6---acesso-a-relatórios-com-sucesso)
- [Cenário de Teste 7 - Acesso a Relatórios com Falha (Permissões)](#cenário-de-teste-7---acesso-a-relatórios-com-falha-permissões)
- [Cenário de Teste 8 - Atualização de Dados do Sistema](#cenário-de-teste-8---atualização-de-dados-do-sistema)

---

## 📝 Descrição dos Casos de Teste

### Cenário de Teste 1 - Login com Dados Inválidos
**ID:** CT-001  
**Título:** Tentativa de Login com Dados Inválidos  

**Pré-condições:**
- O usuário não está logado.
- O usuário possui ou não uma conta cadastrada.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de login | Tela de login é carregada corretamente. |
| 2     | Insira um email válido e uma senha incorreta e clique em "Entrar" | Mensagem de erro: "Usuário ou senha inválidos. Tente novamente." |
| 3     | Insira um email inexistente no campo de email e clique em "Entrar" | Mensagem de erro: "Usuário não encontrado. Tente novamente." |
| 4     | Tente fazer login sem preencher os campos obrigatórios | Mensagem de erro: "Campos obrigatórios não preenchidos." |

**Pós-condições:**
- O usuário permanece na tela de login.

---

### Cenário de Teste 2 - Cadastro de Novo Usuário com Dados Incompletos
**ID:** CT-002  
**Título:** Cadastro de Novo Usuário com Dados Incompletos  

**Pré-condições:**
- O usuário não está logado.
- Nenhuma conta foi cadastrada.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de cadastro | Tela de cadastro é carregada corretamente. |
| 2     | Deixe o campo de nome vazio e clique em "Cadastrar" | Mensagem de erro: "Nome é obrigatório." |
| 3     | Deixe o campo de email vazio e clique em "Cadastrar" | Mensagem de erro: "Email é obrigatório." |
| 4     | Preencha um email inválido (ex: "email@semformato") e clique em "Cadastrar" | Mensagem de erro: "Formato de email inválido." |
| 5     | Preencha senha e confirmação de senha diferentes e clique em "Cadastrar" | Mensagem de erro: "As senhas não coincidem." |

**Pós-condições:**
- Nenhuma conta é criada com dados inválidos.

---

### Cenário de Teste 3 - Cadastro de Novo Usuário com Dados Válidos
**ID:** CT-003  
**Título:** Cadastro de Novo Usuário com Dados Válidos  

**Pré-condições:**
- O usuário não está logado.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de cadastro | Tela de cadastro é carregada corretamente. |
| 2     | Preencha todos os campos obrigatórios com dados válidos | Campos aceitam os dados inseridos corretamente. |
| 3     | Clique no botão "Cadastrar" | Usuário cadastrado com sucesso e redirecionado para a página inicial. |

**Pós-condições:**
- O usuário é redirecionado para a página principal com sucesso.

---

### Cenário de Teste 4 - Edição de Usuário com Dados Inválidos
**ID:** CT-004  
**Título:** Tentativa de Edição de Usuário com Dados Inválidos  

**Pré-condições:**
- Usuário logado com permissão de administrador.
- Existem usuários cadastrados.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de usuários | Página de usuários é carregada corretamente. |
| 2     | Selecione um usuário para editar | Página de edição de usuário é carregada. |
| 3     | Deixe o campo de nome vazio e clique em "Salvar" | Mensagem de erro: "Nome não pode ser vazio." |
| 4     | Preencha o campo de email com um formato inválido e clique em "Salvar" | Mensagem de erro: "Formato de email inválido." |
| 5     | Tente salvar sem alterar os campos obrigatórios | Nenhuma alteração é feita e a mensagem "Nada foi alterado." é exibida. |

**Pós-condições:**
- As alterações não são salvas em caso de dados inválidos.

---

### Cenário de Teste 5 - Exclusão de Usuário
**ID:** CT-005  
**Título:** Exclusão de Usuário  

**Pré-condições:**
- Usuário logado com permissão de administrador.
- Existem usuários cadastrados.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de usuários | Página de usuários é carregada corretamente. |
| 2     | Selecione um usuário para excluir | Página de detalhes do usuário é carregada. |
| 3     | Clique no botão "Excluir" e confirme a exclusão | O usuário é removido da lista de usuários com sucesso. |

**Pós-condições:**
- O usuário é excluído permanentemente do sistema.

---

### Cenário de Teste 6 - Acesso a Relatórios com Sucesso
**ID:** CT-006  
**Título:** Acesso a Relatórios com Dados Válidos  

**Pré-condições:**
- Usuário logado com permissões adequadas.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de relatórios | Página de relatórios é carregada corretamente. |
| 2     | Selecione o tipo de relatório desejado (ex: Relatório de Vendas) | Relatório é exibido corretamente na tela. |
| 3     | Verifique os dados no relatório | Dados estão corretos e atualizados. |

**Pós-condições:**
- O relatório é exibido com todos os dados corretamente.

---

### Cenário de Teste 7 - Acesso a Relatórios com Falha (Permissões)
**ID:** CT-007  
**Título:** Acesso a Relatórios com Permissões Insuficientes  

**Pré-condições:**
- Usuário logado com permissões limitadas (não administrador).

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de relatórios | Página de relatórios é carregada. |
| 2     | Tente acessar um relatório restrito | Mensagem de erro: "Permissão negada. Você não tem acesso a este relatório." |

**Pós-condições:**
- O usuário não consegue acessar relatórios restritos.

---

### Cenário de Teste 8 - Atualização de Dados do Sistema
**ID:** CT-008  
**Título:** Atualização de Configurações do Sistema  

**Pré-condições:**
- Usuário logado com permissões de administrador.

| Passo | Descrição | Resultado Esperado |
|-------|-----------|--------------------|
| 1     | Acesse a página de configurações do sistema | Página de configurações é carregada. |
| 2     | Altere uma configuração e clique em "Salvar" | Configuração é salva com sucesso. |
| 3     | Verifique se a alteração foi aplicada | A configuração é refletida corretamente no sistema. |

**Pós-condições:**
- A configuração do sistema foi alterada e aplicada.

---

## 🔍 Observações

### Ambiente de Teste:
- Certifique-se de que o ambiente de testes é consistente, com todos os dados necessários carregados e as permissões de usuário configuradas corretamente.

