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

* # Especificação de Arquitetura de Software: Sistema de Gestão do Guia de Ensino e Aprendizagem (SG-GEA)
## Abordagem Serverless Zero-Custo (Google Workspace for Education & Apps Script)

Este documento detalha a arquitetura técnica, os componentes de hardware/software e os fluxos de integração para o sistema de automatização do Guia de Ensino e Aprendizagem, projetado especificamente para uma **escola estadual** utilizando recursos 100% gratuitos do ecossistema Google.

---

## 💻 1. Componentes de Hardware e Infraestrutura

Como a solução é baseada inteiramente em computação em nuvem (*Cloud-Native* e *Serverless*), a instituição não necessita de servidores locais, infraestrutura de rede complexa ou gastos com manutenção de TI.

### Dispositivos dos Utilizadores (Clientes)
* **Computadores e Chromebooks da Escola:** Dispositivos locais utilizados pelos professores no planeamento e pela coordenação na validação dentro do ambiente escolar.
* **Dispositivos Móveis e Computadores Pessoais:** Smartphones (Android/iOS) e portáteis utilizados por docentes e alunos para acesso remoto (em casa ou via Wi-Fi da escola).

### Servidores na Nuvem (Infraestrutura Google)
* **Google Cloud Servers:** Data centers globais da Google que processam o código, gerem a autenticação, alojam os ficheiros e garantem alta disponibilidade (24/7) com custo zero para contas educacionais.

---

## 🛠️ 2. Stack Tecnológica (Tecnologias Utilizadas)

A arquitetura utiliza exclusivamente as ferramentas do **Google Workspace for Education**, aproveitando as licenças gratuitas já fornecidas às escolas estaduais.

| Camada | Tecnologia / Ferramenta | Função no Sistema | Custos |
| :--- | :--- | :--- | :--- |
| **Interface (Front-End)** | Google Forms / HTML5 + CSS3 via Apps Script | Captura dos dados pedagógicos inseridos pelos professores através de um formulário intuitivo. | R$ 0,00 |
| **Cérebro (Back-End)** | Google Apps Script (Baseado em JavaScript) | Execução da lógica de negócio, automação de fluxos, geração de documentos e envio de e-mails. | R$ 0,00 |
| **Banco de Dados** | Google Sheets (Planilhas Google) | Armazenamento estruturado de todos os guias preenchidos, comentários e estados de aprovação. | R$ 0,00 |
| **Segurança / Login** | Google OAuth 2.0 (Contas Institucionais) | Autenticação obrigatória. Restringe o acesso apenas a e-mails autorizados do domínio do Estado. | R$ 0,00 |
| **Armazenamento** | Google Drive & Google Docs | Geração de templates dinâmicos e armazenamento dos Guias finais em formato PDF não editável. | R$ 0,00 |
| **Notificações** | Gmail Service (via Apps Script) | Disparo automático de e-mails de alerta para a coordenação e alertas de correção para professores. | R$ 0,00 |

---

## 🔄 3. Relacionamento e Fluxo da Informação (Dataflow)

O relacionamento entre os componentes ocorre através de gatilhos automáticos (*triggers*) orientados a eventos, divididos em quatro etapas principais:

### 1. Submissão e Autenticação
* O **Professor** acede ao formulário. O sistema valida a identidade através do **Google OAuth 2.0**.
* O formulário recolhe os dados estruturados (Justificativa, Conteúdos, Habilidades, Recursos, etc.).

### 2. Processamento e Persistência
* Ao clicar em "Enviar", os dados são registados numa nova linha do **Google Sheets** (Banco de Dados).
* Este evento ativa um gatilho (*OnFormSubmit*) no **Google Apps Script**.
* O Script lê os dados da linha, acede a um modelo base no **Google Docs**, substitui os campos variáveis (ex: `{{justificativa}}`) e gera um documento formatado.

### 3. Workflow de Aprovação
* O Script utiliza o serviço do **Gmail** para enviar uma notificação ao **Coordenador Pedagógico**.
* O Coordenador analisa o documento e, diretamente pela planilha ou por uma interface simples, altera o estado para `Aprovado` ou `Necessita de Ajustes`.

### 4. Publicação e Consulta
* Se o estado for alterado para `Aprovado`, o **Apps Script** converte o Google Doc em **PDF** de forma automática.
* O arquivo PDF é movido para uma pasta partilhada pública no **Google Drive**.
* Os **Estudantes** acedem à pasta através de um link partilhado para consultar o planeamento do trimestre.

---

## 🛡️ 4. Segurança, Limites e Viabilidade

* **Segurança de Dados:** O acesso ao ecossistema está protegido pela criptografia padrão do Google. Nenhuma pessoa externa ao domínio institucional pode visualizar os dados ou submeter formulários.
* **Limites de Cota (Quotas):** As contas do Google Workspace for Education possuem limites diários generosos (ex: até 1500 e-mails automáticos por dia e criação massiva de ficheiros). O fluxo de uma escola estadual consumirá menos de 5% destas cotas gratuitas.
* **Manutenção:** Como não existem servidores físicos ou serviços de alojamento pagos (como AWS, Azure ou GCP tradicional), o custo de manutenção técnica a longo prazo é nulo.
