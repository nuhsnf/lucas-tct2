# Especificação de Requisitos: Sistema de Gestão do Guia de Ensino e Aprendizagem (SG-GEA)

Este documento apresenta a especificação e definição de escopo para o desenvolvimento de um sistema digital destinado a substituir o formulário físico ou em documento de texto (Word/PDF) do **Guia de Ensino e de Aprendizagem do Itinerário Formativo do EMTI Propedêutico**.

---

## 🎯 1. Objetivo do Sistema

O objetivo principal do sistema é **automatizar, centralizar e padronizar** o processo de planeamento, criação, validação e consulta dos Guias de Ensino e Aprendizagem. 

A plataforma transforma um fluxo atualmente manual e descentralizado numa aplicação web intuitiva, garantindo que as diretrizes pedagógicas sejam seguidas com eficiência, promovendo a colaboração entre docentes e a transparência para toda a comunidade escolar.

---

## 🔍 2. Propósito do Sistema e Problemas Resolvidos

### Para que serve o sistema?
* **Digitalização Inteligente:** Transforma campos estáticos em formulários dinâmicos e autoexplicativos.
* **Integração Curricular:** Disponibiliza menus de seleção com as competências e habilidades oficiais da BNCC e dos referenciais curriculares estaduais/municipais.
* **Fluxo de Trabalho (Workflow) Pedagógico:** Cria um canal direto de envio, revisão e aprovação entre professores e coordenadores.
* **Repositório Histórico:** Mantém uma base de conhecimento onde planos antigos podem ser consultados, duplicados e adaptados para novos anos letivos.

### Que problemas resolve?
* **Desdesperdício de Tempo com Formatação:** Liberta os professores da tarefa de ajustar tabelas, margens e fontes em editores de texto tradicionais.
* **Inconsistência de Dados e Erros:** Elimina guias entregues com campos obrigatórios em branco ou com códigos de habilidades digitados incorretamente.
* **Informação Descentralizada:** Acaba com a perda de ficheiros em computadores pessoais, pens USB ou impressões físicas perdidas nos arquivos da escola.
* **Falta de Monitorização:** Resolve a dificuldade da coordenação pedagógica em saber, em tempo real, quais os professores que já submeteram os planos e quais os que estão em atraso.

---

## 👥 3. Perfis de Utilizadores

O sistema possui três níveis de acesso, cada um com permissões e visões específicas:

### 1. Professor(a) (Utilizador Operacional)
* **Ações no Sistema:** Preencher novos guias através de um assistente passo a passo; selecionar habilidades pré-cadastradas; duplicar guias de trimestres anteriores; visualizar o histórico de revisões; responder ao feedback da coordenação.
* **Principal Benefício:** Agilidade na escrita pedagógica e reutilização de conteúdos.

### 2. Coordenador(a) Pedagógico(a) / Especialista (Utilizador Validador)
* **Ações no Sistema:** Visualizar o painel geral de entregas da escola; analisar os guias submetidos; inserir comentários pontuais em campos específicos; aprovar ou devolver para correções; exportar relatórios consolidados.
* **Principal Benefício:** Controlo total sobre a qualidade do planeamento e prazos da instituição.

### 3. Estudante (Utilizador Consultor)
* **Ações no Sistema:** Consultar em modo de leitura os guias aprovados das disciplinas em que está matriculado.
* **Principal Benefício:** Transparência no processo de aprendizagem, permitindo ao aluno saber antecipadamente as atividades cooperativas, os espaços que irá utilizar e como será avaliado.

---

## 📑 4. Definição do Escopo do Projeto

### O que FAZ PARTE do sistema (Escopo Incluído):
* **Autenticação e Gestão de Perfil:** Login seguro com níveis de acesso diferenciados (Professor, Coordenador, Estudante).
* **Módulo de Criação de Guias:** Formulário dividido por secções (Justificativa, Habilidades, Situações Didáticas, etc.) com salvamento automático.
* **Banco de Dados de Competências:** Cadastro centralizado das habilidades cognitivas, socioemocionais e gerais para seleção rápida via tags ou caixas de seleção.
* **Módulo de Avaliação Pedagógica:** Espaço para comentários e alteração de status do documento (*Rascunho*, *Enviado para Análise*, *Ajustes Necessários*, *Aprovado*).
* **Exportação:** Geração de documento PDF formatado e padronizado com um clique.

### O que NÃO FAZ PARTE do sistema (Escopo Excluído):
* **Lançamento de Notas e Faltas:** O sistema é focado exclusivamente no planeamento (Guia de Ensino); não substituirá o Diário de Classe eletrónico.
* **Ambiente Virtual de Aprendizagem (AVA):** O sistema não hospedará aulas online, fóruns de discussão ou entrega de tarefas por parte dos estudantes.
* **Gestão de Horários das Aulas:** O mapeamento de horários e alocação física de salas não serão geridos por esta ferramenta nesta primeira fase.
