# 3. DOCUMENTO DE ESPECIFICAÇÃO DE REQUISITOS DE SOFTWARE

Este documento descreve os requisitos do sistema **GreenDrop – Sistema de Descarte Correto de Materiais**, incluindo funcionalidades, restrições, usuários e modelagem do sistema, com foco em empresas e organizações que necessitam realizar descartes de forma adequada.

## 3.1 Objetivo do Documento
O objetivo deste documento é apresentar a concepção e a proposta do sistema **GreenDrop**, detalhando o contexto do problema, público-alvo, objetivos do sistema, principais funcionalidades, requisitos funcionais e não funcionais, usuários, modelagem e diagramas.  
Este documento serve como referência para o planejamento, desenvolvimento e implantação do sistema, fornecendo uma visão estruturada para todos os envolvidos.

## 3.2 Escopo do Produto

### 3.2.1 Nome do produto e seus componentes principais
O produto será denominado **GreenDrop – Sistema de Descarte Correto de Materiais**.  
Módulos principais:
- Cadastro de Empresas  
- Cadastro de Materiais  
- Pontos de Coleta  
- Relatórios e Consultas  
- Autenticação e Permissões  
- Atendimento Inteligente (Bot de IA)  

### 3.2.2 Missão do produto
Facilitar o descarte correto de materiais recicláveis e/ou especiais pelas empresas, oferecendo informações sobre pontos de coleta, relatórios de controle e orientações de sustentabilidade.  
Além disso, fornecer suporte automatizado via bot de IA, que responde dúvidas sobre reciclabilidade e indica o ponto de coleta mais próximo.

### 3.2.3 Limites do produto
- Não realiza a coleta física dos materiais.  
- Não comercializa resíduos, limitando-se à gestão de informações.  
- Exclusivo para empresas, não atendendo pessoas físicas.  
- Não gerencia transporte ou logística dos materiais.

### 3.2.4 Benefícios do produto

| # | Benefício | Valor para o Cliente |
|---|------------------------------------|------------------|
| 1 | Cadastro simplificado de empresas e materiais | Essencial |
| 2 | Localização fácil de pontos de coleta | Essencial |
| 3 | Geração de relatórios ambientais | Essencial |
| 4 | Disseminação de informações sobre sustentabilidade | Recomendável |
| 5 | Cumprimento da legislação ambiental vigente | Essencial |
| 6 | Atendimento automatizado via Bot de IA | Diferencial |

## 3.3 Descrição Geral do Produto

### 3.3.1 Requisitos Funcionais

| Código | Requisito Funcional | Descrição |
|--------|-------------------|-----------|
| RF1 | Gerenciar Empresas | Inclusão, alteração, exclusão e consulta de empresas cadastradas |
| RF2 | Gerenciar Materiais | Inclusão, alteração, exclusão e consulta de materiais descartáveis |
| RF3 | Gerenciar Pontos de Coleta | Inclusão, alteração, exclusão e consulta de pontos de coleta |
| RF4 | Gerar Relatórios | Relatórios de descarte por empresa, material e ponto de coleta |
| RF5 | Gerenciar Usuários | Inclusão, alteração e exclusão de contas de usuários vinculados às empresas |
| RF6 | Login e Autenticação | Acesso restrito ao sistema via login e senha |
| RF7 | Consultar Informações | Empresas podem consultar informações sobre descarte correto e legislação ambiental |
| RF8 | Atendimento via Bot de IA | Responde dúvidas sobre reciclabilidade e indica pontos de coleta mais próximos |

### 3.3.2 Requisitos Não Funcionais

| Código | Requisito Não Funcional |
|--------|-----------------------|
| RNF1 | Sistema web, acessível por navegadores modernos (Chrome, Firefox, Edge, Safari) |
| RNF2 | Responsivo para desktop e dispositivos móveis |
| RNF3 | Autenticação individual de usuários |
| RNF4 | Suporta até 500 usuários simultâneos |
| RNF5 | Disponível 24/7, exceto durante manutenção |

### 3.3.3 Usuários 

| Ator | Descrição |
|------|-----------|
| Administrador | Gerencia empresas, pontos de coleta e usuários; acesso total |
| Empresa | Cadastra materiais e consulta pontos de coleta |
| Colaborador da Empresa | Registra descartes e gera relatórios |
| Ponto de Coleta | Recebe materiais das empresas parceiras |
| Bot de IA | Interpreta dúvidas e indica pontos de coleta corretos |

## 3.4 Modelagem do Sistema

### 3.4.1 Diagrama de Casos de Uso
Como observado no diagrama de casos de uso da Figura 1, a secretária poderá gerenciar as matrículas e professores no sistema, enquanto o coordenador, além dessas funções, poderá gerenciar os cursos de aperfeiçoamento.

#### Figura 1: Diagrama de Casos de Uso do Sistema.

![dcu](https://github.com/user-attachments/assets/41f6b731-b44e-43aa-911f-423ad6198f47)
 
### 3.4.2 Descrições de Casos de Uso

Cada caso de uso deve ter a sua descrição representada nesta seção. Exemplo:

#### Gerenciar Professor (CSU01)

Sumário: A Secretária realiza a gestão (inclusão, remoção, alteração e consulta) dos dados sobre professores.

Ator Primário: Secretária.

Ator Secundário: Coordenador.

Pré-condições: A Secretária deve ser validada pelo Sistema.

Fluxo Principal:

1) 	A Secretária requisita manutenção de professores.
2) 	O Sistema apresenta as operações que podem ser realizadas: inclusão de um novo professor, alteração de um professor, a exclusão de um professor e a consulta de dados de um professor.
3) 	A Secretária seleciona a operação desejada: Inclusão, Exclusão, Alteração ou Consulta, ou opta por finalizar o caso de uso.
4) 	Se a Secretária desejar continuar com a gestão de professores, o caso de uso retorna ao passo 2; caso contrário o caso de uso termina.

Fluxo Alternativo (3): Inclusão

a)	A Secretária requisita a inclusão de um professor. <br>
b)	O Sistema apresenta uma janela solicitando o CPF do professor a ser cadastrado. <br>
c)	A Secretária fornece o dado solicitado. <br>
d)	O Sistema verifica se o professor já está cadastrado. Se sim, o Sistema reporta o fato e volta ao início; caso contrário, apresenta um formulário em branco para que os detalhes do professor (Código, Nome, Endereço, CEP, Estado, Cidade, Bairro, Telefone, Identidade, Sexo, Fax, CPF, Data do Cadastro e Observação) sejam incluídos. <br>
e)	A Secretária fornece os detalhes do novo professor. <br>
f)	O Sistema verifica a validade dos dados. Se os dados forem válidos, inclui o novo professor e a grade listando os professores cadastrados é atualizada; caso contrário, o Sistema reporta o fato, solicita novos dados e repete a verificação. <br>

Fluxo Alternativo (3): Remoção

a)	A Secretária seleciona um professor e requisita ao Sistema que o remova. <br>
b)	Se o professor pode ser removido, o Sistema realiza a remoção; caso contrário, o Sistema reporta o fato. <br>

Fluxo Alternativo (3): Alteração

a)	A Secretária altera um ou mais dos detalhes do professor e requisita sua atualização. <br>
b)	O Sistema verifica a validade dos dados e, se eles forem válidos, altera os dados na lista de professores, caso contrário, o erro é reportado. <br>
 
Fluxo Alternativo (3): Consulta

a)	A Secretária opta por pesquisar pelo nome ou código e solicita a consulta sobre a lista de professores. <br>
b)	O Sistema apresenta uma lista professores. <br>
c)	A Secretária seleciona o professor. <br>
d)	O Sistema apresenta os detalhes do professor no formulário de professores. <br>

Pós-condições: Um professor foi inserido ou removido, seus dados foram alterados ou apresentados na tela.

### 3.4.3 Diagrama de Classes 

A Figura 2 mostra o diagrama de classes do sistema. A Matrícula deve conter a identificação do funcionário responsável pelo registro, bem com os dados do aluno e turmas. Para uma disciplina podemos ter diversas turmas, mas apenas um professor responsável por ela.

#### Figura 2: Diagrama de Classes do Sistema.
 
![image](https://github.com/user-attachments/assets/abc7591a-b46f-4ea2-b8f0-c116b60eb24e)


### 3.4.4 Descrições das Classes 

| # | Nome | Descrição |
|--------------------|------------------------------------|----------------------------------------|
| 1	|	Aluno |	Cadastro de informações relativas aos alunos. |
| 2	| Curso |	Cadastro geral de cursos de aperfeiçoamento. |
| 3 |	Matrícula |	Cadastro de Matrículas de alunos nos cursos. |
| 4 |	Turma |	Cadastro de turmas.
| 5	|	Professor |	Cadastro geral de professores que ministram as disciplinas. |
| ... |	... |	... |
