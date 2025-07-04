#Modelagem de Banco de Dados para Biblioteca Universitária (MySQL Workbench)

#Descrição  
Projeto acadêmico desenvolvido para a disciplina de **Modelagem de Dados**, onde modelei um sistema de gerenciamento de empréstimos de livros usando **MySQL Workbench**. O diagrama DER (Entidade-Relacionamento) representa as relações entre **Alunos, Livros, Colaboradores e Empréstimos**, seguindo regras de negócio reais.  

#Tecnologias  
- **Ferramenta:** MySQL Workbench  
- **Linguagem:** SQL  
- **Conceitos aplicados:**  
  - Normalização de dados  
  - Relacionamentos (1:N, N:M)  
  - Chaves primárias e estrangeiras  

#Diagrama DER  
[Diagrama DER da Biblioteca] (diagramas/modelagem_dados.png)

## 💡 Consultas SQL Exemplo  
```sql
-- Livros emprestados para um aluno específico:
SELECT l.titulo, e.data_emprestimo  
FROM Emprestimo e  
JOIN Livro l ON e.livro_id = l.id  
WHERE e.aluno_id = 123;  

-- Total de empréstimos por colaborador:
SELECT c.nome, COUNT(e.id) AS total_emprestimos  
FROM Colaborador c  
JOIN Emprestimo e ON c.id = e.colaborador_id  
GROUP BY c.nome;  
