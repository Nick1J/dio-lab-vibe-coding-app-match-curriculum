# dio-lab-vibe-coding-app-match-curriculum
Descrição do app de analise de curriculos de usuário ATS Frendly

# Match Curriculum – Pitch Inicial

O App **MatchCV** tem como obejtivo fazer analise do curriculum do usuário usando informações com base na descrição da vaga pretendida. O app faz um matchmarking de vagas de emprego e cria curriculos personalizados ATS Friendly para a vaga pretendida.

---
## 1. Prompt usando ChatGPT
```txt
Quero criar outro aap 100% no lovable, para fazer matchmaking de vagas de emprego e criar versões do curriculum do usuário que sejam ATS friendly para essa vaga. quero que use ShadCN como designe system quero nas cores azul celeste, vermelho e branco me enviem um prompt único em Markdown
```

---

## 2. Prompt gerado no ChatGPT para uso no Lovable
```markdown
# MatchCV — Plataforma Inteligente de Match de Vagas e Currículos ATS

## 1. Visão geral do produto

Crie uma aplicação SaaS web chamada **MatchCV**, desenvolvida 100% no Lovable.

A aplicação deve funcionar **sem cadastro, sem login e sem autenticação**.

O usuário deve acessar o site e começar a utilizar imediatamente.

O objetivo da plataforma é ajudar candidatos a:

* Criar e manter um currículo-base.
* Adicionar uma vaga de emprego.
* Analisar automaticamente a compatibilidade entre seu currículo e a vaga.
* Identificar requisitos atendidos.
* Identificar requisitos ausentes ou pouco evidenciados.
* Identificar palavras-chave relevantes.
* Gerar uma versão personalizada do currículo para aquela vaga.
* Criar currículos preparados para leitura por sistemas ATS.
* Exportar o currículo em PDF.
* Acompanhar candidaturas.
* Manter histórico de currículos e vagas analisadas.

A proposta central do produto é:

**"Seu currículo certo para a vaga certa."**

---

# 2. Experiência sem cadastro

O usuário deve entrar diretamente no aplicativo.

Não criar:

* Tela de cadastro.
* Tela de login.
* Recuperação de senha.
* Autenticação.
* Confirmação de email.
* Onboarding obrigatório.

Ao acessar a aplicação:

`/`

mostrar diretamente o **Dashboard principal do MatchCV**.

O primeiro uso deve apresentar uma experiência simples para começar.

Exemplo:

**Bem-vindo ao MatchCV**

**Analise uma vaga, descubra seu nível de compatibilidade e adapte seu currículo para ela.**

Botões:

**Criar meu currículo**

**Analisar uma vaga**

---

# 3. Persistência dos dados

Como não existe autenticação nesta versão, utilizar **persistência local no navegador**.

Priorizar:

* localStorage para configurações e dados simples;
* IndexedDB quando necessário para conteúdos maiores;
* armazenamento local dos currículos;
* armazenamento local das vagas;
* armazenamento local das análises;
* armazenamento local das candidaturas.

Criar uma camada de persistência abstraída, por exemplo:

`/services/storage`

Criar funções como:

* saveProfile()
* getProfile()
* saveResume()
* getResumes()
* saveJob()
* getJobs()
* saveMatch()
* getMatches()
* saveApplication()
* getApplications()
* saveGeneratedResume()
* getGeneratedResumes()

A aplicação não deve espalhar chamadas diretas ao localStorage por diversos componentes.

Centralizar o acesso aos dados.

Preparar a arquitetura para que no futuro seja possível substituir a persistência local por Supabase ou outro backend sem reescrever toda a interface.

---

# 4. Importante sobre dados locais

Informar de forma discreta nas configurações:

**"Seus dados estão armazenados neste dispositivo."**

Adicionar uma opção:

**Exportar meus dados**

Gerar um arquivo JSON contendo os dados do usuário.

Adicionar também:

**Importar meus dados**

Permitir que o usuário restaure seus dados em outro navegador/dispositivo.

Adicionar:

**Apagar todos os meus dados**

Exigir confirmação antes de apagar.

---

# 5. Stack e padrões técnicos

Utilize:

* React
* TypeScript
* Vite
* Tailwind CSS
* **ShadCN UI como Design System principal**
* Lucide Icons
* Arquitetura preparada para integração com IA
* Componentes reutilizáveis
* Design responsivo
* Código organizado e escalável

Priorizar componentes nativos do ShadCN sempre que possível.

Utilizar:

* Button
* Card
* Badge
* Input
* Textarea
* Select
* Dialog
* Sheet
* Tabs
* Accordion
* Progress
* Alert
* Dropdown Menu
* Avatar
* Tooltip
* Table
* Separator
* Skeleton
* Sonner
* Command
* Checkbox
* Radio Group
* Switch

---

# 6. Identidade visual

Utilizar uma identidade visual baseada em:

### Azul celeste

`#38BDF8`

Cor principal da aplicação.

Utilizar para:

* Botões principais
* Links
* Destaques
* Progress bars
* Indicadores
* Estados selecionados
* Ícones importantes

### Azul escuro

`#0F172A`

Utilizar para:

* Títulos
* Textos principais
* Navegação
* Elementos de alto contraste

### Vermelho

`#EF4444`

Utilizar moderadamente para:

* Alertas
* Erros
* Lacunas importantes
* Baixa compatibilidade
* Ações destrutivas

### Branco

`#FFFFFF`

Utilizar como principal cor de cards e áreas de conteúdo.

### Fundo

Utilizar aproximadamente:

`#F8FAFC`

A interface deve transmitir:

* Tecnologia
* Inteligência artificial
* Empregabilidade
* Confiança
* Profissionalismo
* Simplicidade

Evitar excesso de gradientes.

Evitar estética excessivamente futurista.

---

# 7. Marca

Nome:

**MatchCV**

Tagline:

**Seu currículo certo para a vaga certa.**

Mensagem:

**Analise vagas, descubra seu nível de compatibilidade e crie currículos personalizados e preparados para sistemas ATS.**

---

# 8. Estrutura geral da aplicação

A aplicação deve ter um layout SaaS moderno.

### Sidebar

Itens:

* Dashboard
* Meu currículo
* Analisar vaga
* Minhas vagas
* Currículos gerados
* Candidaturas
* Meu perfil
* Configurações

### Header

Mostrar:

* Nome MatchCV
* Título da página atual
* Avatar genérico ou iniciais
* Menu de opções

Como não existe login, não mostrar nome de usuário no header por padrão.

---

# 9. Dashboard

A primeira tela da aplicação deve ser o dashboard.

Título:

**Olá, vamos encontrar sua próxima oportunidade.**

Subtítulo:

**Analise uma vaga e descubra como seu currículo se encaixa nela.**

---

## Ações principais

Criar duas ações em destaque:

### Criar currículo

Descrição:

**Monte seu currículo-base para usar em diferentes vagas.**

### Analisar vaga

Descrição:

**Compare seu perfil com os requisitos de uma vaga.**

---

# 10. Cards do dashboard

Mostrar:

### Meu currículo

Exemplo:

**92% completo**

Botão:

**Editar currículo**

---

### Vagas analisadas

Exemplo:

**8**

Botão:

**Ver minhas vagas**

---

### Currículos gerados

Exemplo:

**5**

Botão:

**Ver currículos**

---

### Candidaturas

Exemplo:

**4**

Botão:

**Acompanhar candidaturas**

---

# 11. Primeiro uso

Quando não existir nenhum dado salvo, mostrar um Empty State no dashboard.

Título:

**Comece criando seu currículo-base**

Descrição:

**Você poderá reutilizar essas informações para analisar diferentes vagas e gerar versões personalizadas do seu currículo.**

Botão:

**Criar meu currículo**

Abaixo:

**Já possui uma vaga?**

Botão:

**Analisar uma vaga**

---

# 12. Meu currículo

Criar área:

**Meu currículo**

O usuário deve poder criar seu currículo-base sem precisar de conta.

---

## Informações pessoais

Campos:

* Nome completo
* Email
* Telefone
* Cidade
* Estado
* LinkedIn
* GitHub
* Portfólio
* Site pessoal

Não exigir foto.

---

# 13. Resumo profissional

Campo grande:

**Resumo profissional**

Botão:

**Melhorar com IA**

A IA pode melhorar a redação mantendo somente informações fornecidas pelo usuário.

Não inventar:

* Experiências
* Resultados
* Cargos
* Tecnologias
* Empresas
* Certificações

---

# 14. Experiência profissional

Permitir cadastrar múltiplas experiências.

Campos:

* Empresa
* Cargo
* Local
* Data de início
* Data de término
* Atualmente trabalho aqui
* Descrição
* Responsabilidades
* Resultados/conquistas

Botão:

**+ Adicionar experiência**

Permitir editar e excluir experiências.

Permitir reordenar experiências.

---

# 15. Formação

Campos:

* Instituição
* Curso
* Grau
* Data de início
* Data de conclusão
* Em andamento

Permitir múltiplas formações.

---

# 16. Habilidades

Criar interface para inserir habilidades.

Exemplos:

* JavaScript
* React
* Excel
* Gestão de projetos
* Atendimento ao cliente

Permitir classificação:

* Técnica
* Comportamental

Mostrar as habilidades como Badges.

---

# 17. Idiomas

Campos:

* Idioma
* Nível

Permitir múltiplos idiomas.

---

# 18. Certificações

Campos:

* Nome
* Instituição
* Data
* Link opcional

---

# 19. Completude do currículo

Mostrar:

**Completude do currículo**

Exemplo:

`92%`

Utilizar Progress do ShadCN.

Mostrar sugestões:

* Adicione pelo menos uma experiência.
* Adicione suas principais habilidades.
* Adicione seu LinkedIn.
* Complete o resumo profissional.

---

# 20. Analisar uma vaga

Criar uma tela chamada:

**Analisar vaga**

Mostrar duas opções.

---

## Opção 1 — Colar descrição da vaga

Textarea grande:

**Cole aqui a descrição completa da vaga**

Placeholder:

"Responsabilidades, requisitos, formação, experiência, habilidades..."

Botão:

**Analisar vaga**

---

## Opção 2 — URL da vaga

Campo:

**URL da vaga**

Botão:

**Importar vaga**

Se a URL não puder ser processada:

**Não conseguimos importar esta vaga automaticamente. Cole a descrição da vaga para continuar.**

---

# 21. Processamento da vaga

A IA deve identificar:

* Cargo
* Empresa
* Localização
* Modalidade
* Senioridade
* Salário, quando disponível
* Requisitos obrigatórios
* Requisitos desejáveis
* Responsabilidades
* Hard skills
* Soft skills
* Formação
* Idiomas
* Certificações
* Palavras-chave

---

# 22. Tela de detalhes da vaga

Mostrar:

### Cargo

### Empresa

### Localização

### Modalidade

### Senioridade

---

## Sobre a vaga

Mostrar descrição organizada.

---

## Requisitos

Separar:

**Obrigatórios**

**Desejáveis**

---

## Competências

Mostrar:

* Hard skills
* Soft skills

---

# 23. Match entre currículo e vaga

Criar página:

**Análise de compatibilidade**

No topo mostrar um indicador grande:

# 87%

**Compatibilidade estimada**

Logo abaixo:

**Esse percentual representa a correspondência entre as informações disponíveis no seu currículo e os requisitos identificados nesta vaga. Não representa uma probabilidade de contratação.**

---

# 24. Breakdown do Match

Mostrar:

### Experiência

92%

### Habilidades técnicas

88%

### Formação

100%

### Palavras-chave

81%

### Idiomas

100%

### Outros requisitos

75%

Utilizar Progress do ShadCN.

Os pesos devem ser configuráveis no código.

---

# 25. Você atende

Criar uma seção:

**Pontos compatíveis**

Exemplos:

* Experiência com React
* Formação compatível
* Experiência profissional relacionada
* Conhecimento de Git

Mostrar cada item como um Card ou Badge.

---

# 26. Atenção

Criar seção:

**Pontos que podem ser melhor evidenciados**

Exemplos:

* A vaga destaca AWS, mas seu currículo não descreve claramente essa experiência.
* A vaga menciona liderança de projetos e seu currículo possui essa experiência, mas ela pode estar pouco destacada.

---

# 27. Lacunas

Criar seção:

**Requisitos não identificados no seu currículo**

Exemplo:

**AWS**

Mensagem:

**Essa competência aparece nos requisitos da vaga, mas não foi identificada nas informações do seu currículo.**

Botão:

**Tenho essa experiência**

Quando o usuário clicar:

abrir campo para adicionar a informação ao currículo.

Nunca adicionar automaticamente uma competência.

---

# 28. Palavras-chave ATS

Criar seção:

**Palavras-chave da vaga**

Separar em:

### Encontradas no currículo

Exibir Badges.

### Não identificadas

Exibir Badges de atenção.

Ao clicar em uma palavra-chave, mostrar:

* Onde ela aparece na vaga.
* Se aparece no currículo.
* Se pode ser relevante para alguma experiência existente.
* Sugestão de onde ela poderia ser mencionada, caso o usuário realmente tenha essa experiência.

---

# 29. Análise ATS

Criar seção:

**Análise de compatibilidade com ATS**

Verificar:

* Estrutura simples.
* Títulos de seção reconhecíveis.
* Organização das experiências.
* Datas consistentes.
* Palavras-chave relevantes.
* Texto selecionável.
* Ausência de tabelas complexas.
* Ausência de caixas de texto.
* Ausência de elementos gráficos desnecessários.
* Hierarquia adequada.

Mostrar:

**Score estrutural ATS: 94/100**

Explicar quais fatores influenciaram o score.

Não apresentar esse score como garantia de aprovação em ATS.

---

# 30. Gerar currículo para a vaga

Criar CTA principal:

**Criar currículo para esta vaga**

Ao clicar, mostrar uma Dialog.

Título:

**Personalizar currículo**

Mostrar:

* Cargo
* Empresa
* Match atual
* Principais pontos fortes
* Pontos a melhorar

Botão:

**Gerar currículo personalizado**

---

# 31. Regras de geração

A IA deve trabalhar exclusivamente com informações verdadeiras fornecidas pelo usuário.

Nunca inventar:

* Empresas
* Cargos
* Experiências
* Projetos
* Tecnologias
* Resultados
* Números
* Certificações
* Formação
* Idiomas
* Habilidades

A IA pode:

* Reorganizar informações.
* Melhorar a redação.
* Adaptar o resumo profissional.
* Destacar experiências mais relevantes.
* Reorganizar habilidades.
* Ajustar palavras-chave verdadeiras.
* Melhorar descrições.
* Priorizar informações relacionadas à vaga.

Regra principal:

**O currículo pode ser adaptado, mas nunca falsificado.**

---

# 32. Editor de currículo personalizado

Depois da geração, abrir o editor.

Layout desktop:

### Painel esquerdo

Editor.

### Painel direito

Preview em tempo real.

No mobile:

Utilizar Tabs:

**Editar**

**Visualizar**

---

# 33. Editor

Permitir:

* Editar textos.
* Editar resumo.
* Editar experiências.
* Editar habilidades.
* Reordenar seções.
* Esconder seções.
* Adicionar seções.
* Alterar template.
* Salvar alterações.

Botões:

**Salvar versão**

**Gerar novamente**

**Exportar PDF**

---

# 34. Templates ATS

Criar inicialmente 3 templates.

## Classic

Tradicional e profissional.

## Modern

Moderno, mantendo estrutura compatível com ATS.

## Minimal

Extremamente simples e objetivo.

Todos devem priorizar:

* Uma coluna.
* Texto bem estruturado.
* Hierarquia clara.
* Títulos tradicionais.
* Boa legibilidade.
* Poucos elementos gráficos.

Evitar:

* Tabelas complexas.
* Barras de habilidade.
* Gráficos.
* Ícones usados para representar informações essenciais.
* Caixas de texto.
* Layouts muito elaborados.
* Colunas múltiplas para informações importantes.

---

# 35. Exportação PDF

Permitir exportar o currículo em PDF.

O PDF deve:

* Ter texto selecionável.
* Ter estrutura simples.
* Possuir boa legibilidade.
* Utilizar títulos claros.
* Evitar elementos que dificultem parsing.
* Ser profissional.

Nome sugerido:

`Nome_Sobrenome_Cargo_Empresa.pdf`

---

# 36. Currículos gerados

Criar página:

**Currículos gerados**

Mostrar:

* Empresa
* Cargo
* Data
* Score de Match
* Template
* Score ATS

Ações:

* Visualizar
* Editar
* Duplicar
* Exportar PDF
* Excluir

---

# 37. Minhas vagas

Criar página:

**Minhas vagas**

Mostrar as vagas já analisadas.

Cada card deve apresentar:

* Cargo
* Empresa
* Local
* Modalidade
* Data
* Match
* Status

Exemplo:

**Analista de Sistemas**

**Empresa XYZ**

**87% de compatibilidade**

Botões:

**Ver análise**

**Criar currículo**

**Registrar candidatura**

---

# 38. Filtros de vagas

Criar filtros:

* Cargo
* Empresa
* Localização
* Remoto
* Híbrido
* Presencial
* Senioridade
* Faixa salarial
* Compatibilidade

Permitir pesquisa por texto.

---

# 39. Candidaturas

Criar um sistema pessoal para acompanhar candidaturas.

Utilizar Kanban.

Colunas:

### Interessado

### Currículo preparado

### Candidatura enviada

### Em análise

### Entrevista

### Oferta

### Encerrada

Permitir mover cards entre as etapas.

---

# 40. Dados de candidatura

Cada candidatura deve armazenar:

* Empresa
* Cargo
* Vaga
* Data da candidatura
* Currículo utilizado
* Status
* Observações
* Próximo passo
* Data do próximo passo

---

# 41. Perfil profissional

Criar página:

**Meu perfil**

O perfil é apenas local e não necessita de autenticação.

Mostrar:

* Nome
* Cargo desejado
* Área
* Localização
* Modalidade
* Senioridade
* Habilidades
* Experiência
* Formação

---

# 42. Configurações

Criar:

## Preferências

* Cargo desejado
* Área profissional
* Localização
* Modalidade
* Senioridade

## Dados

### Exportar meus dados

Gerar JSON.

### Importar meus dados

Permitir upload de JSON.

### Apagar todos os dados

Exigir confirmação em Dialog.

Texto:

**Esta ação apagará todos os currículos, vagas, análises e candidaturas armazenados neste navegador.**

Botão:

**Apagar definitivamente**

---

# 43. Inteligência Artificial

Criar uma camada isolada:

`/services/ai`

Funções:

* analyzeJob()
* analyzeResume()
* calculateMatch()
* generateResume()
* improveSummary()
* analyzeATS()

As funções devem ser independentes da interface.

A arquitetura deve permitir trocar o provedor de IA posteriormente.

Preferir respostas estruturadas em JSON.

---

# 44. Processos de IA

Durante análise mostrar estados claros.

Exemplo:

**Analisando a vaga...**

Depois:

**Identificando requisitos...**

Depois:

**Comparando com seu currículo...**

Depois:

**Identificando palavras-chave...**

Depois:

**Preparando sua análise...**

Na geração:

**Adaptando seu currículo...**

**Ajustando palavras-chave...**

**Otimizando estrutura...**

**Finalizando currículo...**

Nunca deixar o usuário sem feedback durante processos demorados.

---

# 45. Sistema de Score

Criar score composto por:

* Experiência: 30%
* Habilidades: 25%
* Formação: 15%
* Palavras-chave: 15%
* Idiomas: 5%
* Outros requisitos: 10%

Centralizar esses pesos em configuração.

Permitir modificar no futuro.

O sistema deve explicar por que determinado score foi calculado.

Não transformar o score em:

* Probabilidade de contratação.
* Previsão de contratação.
* Garantia de entrevista.
* Garantia de aprovação.

---

# 46. Plano Freemium preparado

Mesmo sem cadastro, estruturar o sistema para permitir monetização futuramente.

## Free

Permitir:

* Criar currículo-base.
* Analisar vagas.
* Match limitado.
* Número limitado de currículos gerados.
* Exportação PDF limitada.

## Pro

Preparar estrutura para:

* Mais análises.
* Mais currículos personalizados.
* Mais exportações.
* Templates premium.
* Análise ATS avançada.
* Recursos avançados de IA.
* Histórico ampliado.

Neste primeiro MVP, não é necessário implementar pagamento.

Criar apenas a estrutura visual para futuramente adicionar assinatura.

---

# 47. Limites do plano Free

Criar um componente:

**Uso deste mês**

Exemplo:

**3 de 5 análises utilizadas**

Utilizar Progress.

Quando estiver próximo do limite:

**Você está próximo do limite mensal.**

CTA:

**Conhecer o Pro**

Como não há login, os limites inicialmente podem ser controlados localmente.

Preparar arquitetura para futuramente utilizar controle no backend.

---

# 48. Landing Page opcional

Como o usuário acessa diretamente a aplicação, o produto principal deve ser o próprio aplicativo.

Caso seja necessário criar uma landing page, ela deve ser simples.

Hero:

**Seu currículo certo para a vaga certa.**

Descrição:

**Compare seu currículo com uma vaga e crie uma versão personalizada, profissional e preparada para ATS.**

CTA:

**Começar agora**

O CTA deve abrir diretamente o aplicativo.

Não pedir cadastro antes de utilizar.

---

# 49. Empty States

Criar estados vazios bem elaborados.

### Nenhum currículo

**Você ainda não criou seu currículo-base.**

Botão:

**Criar currículo**

### Nenhuma vaga

**Você ainda não analisou nenhuma vaga.**

Botão:

**Analisar vaga**

### Nenhuma candidatura

**Você ainda não registrou nenhuma candidatura.**

Botão:

**Adicionar candidatura**

---

# 50. Responsividade

A aplicação deve funcionar perfeitamente em:

* Desktop
* Tablet
* Mobile

No mobile:

* Sidebar vira menu lateral.
* Cards adaptam largura.
* Editor de currículo usa Tabs.
* Kanban permite scroll horizontal.
* Tabelas devem possuir comportamento responsivo.

---

# 51. Acessibilidade

Seguir boas práticas:

* Contraste adequado.
* Labels nos inputs.
* Navegação por teclado.
* Estados de foco.
* aria-label quando necessário.
* Não depender somente das cores para representar informações.
* Textos alternativos quando houver imagens.

---

# 52. UX

A experiência deve ter o mínimo possível de fricção.

O usuário deve conseguir começar imediatamente.

O fluxo principal deve ser:

**Abrir app → criar currículo → adicionar vaga → analisar match → entender compatibilidade → identificar lacunas → gerar currículo personalizado → revisar → exportar → registrar candidatura.**

---

# 53. Microcopy

Utilizar português do Brasil.

Tom:

* Profissional
* Claro
* Moderno
* Direto
* Útil

Nunca prometer emprego.

Evitar:

"Garanta sua contratação."

Preferir:

"Melhore a compatibilidade do seu currículo com esta vaga."

Evitar:

"Você será aprovado pelo ATS."

Preferir:

"Seu currículo apresenta uma estrutura mais adequada para leitura automatizada."

---

# 54. Rotas

Criar:

`/`

`/dashboard`

`/resume`

`/resume/:id`

`/jobs`

`/jobs/new`

`/jobs/:id`

`/jobs/:id/match`

`/generated-resumes`

`/generated-resumes/:id`

`/applications`

`/profile`

`/settings`

Não criar rotas:

`/login`

`/register`

`/forgot-password`

`/onboarding`

---

# 55. Componentes reutilizáveis

Criar componentes:

* AppSidebar
* AppHeader
* PageHeader
* StatCard
* MatchScore
* MatchBreakdown
* KeywordBadge
* RequirementCard
* ResumeSection
* ResumePreview
* ResumeEditor
* JobCard
* ApplicationCard
* ApplicationKanban
* ATSScore
* ProfileCompletion
* EmptyState
* LoadingState
* UpgradeCard
* DataExportDialog
* DeleteDataDialog

Utilizar ShadCN sempre que aplicável.

---

# 56. Estrutura de dados local

Criar tipos TypeScript organizados.

Exemplo:

```typescript
type Profile = {
  fullName: string;
  email?: string;
  phone?: string;
  city?: string;
  state?: string;
  linkedinUrl?: string;
  githubUrl?: string;
  portfolioUrl?: string;
  desiredRole?: string;
  desiredArea?: string;
  workMode?: string;
  seniority?: string;
};

type Resume = {
  id: string;
  name: string;
  summary?: string;
  template: "classic" | "modern" | "minimal";
  version: number;
  isBaseResume: boolean;
};

type Job = {
  id: string;
  title: string;
  company?: string;
  location?: string;
  workMode?: string;
  seniority?: string;
  description: string;
  sourceUrl?: string;
};

type JobMatch = {
  id: string;
  jobId: string;
  resumeId: string;
  overallScore: number;
  experienceScore: number;
  skillsScore: number;
  educationScore: number;
  keywordScore: number;
  languageScore: number;
};

type Application = {
  id: string;
  jobId: string;
  generatedResumeId?: string;
  status:
    | "interested"
    | "resume_ready"
    | "applied"
    | "review"
    | "interview"
    | "offer"
    | "closed";
  appliedAt?: string;
  notes?: string;
  nextStep?: string;
  nextStepDate?: string;
};


Adaptar a estrutura conforme a implementação real.



# 57. Futuro backend

Não implementar autenticação agora.

Entretanto, organizar o código para permitir futuramente:

* Supabase Auth
* Banco de dados remoto
* Sincronização entre dispositivos
* Backup em nuvem
* Assinaturas
* Controle de plano
* Analytics

A mudança futura para contas de usuário deve ser possível sem reconstruir o produto inteiro.

---

# 58. Futuras integrações

Preparar arquitetura para posteriormente integrar:

* LinkedIn
* Portais de emprego
* APIs de vagas
* Sistemas de pagamento
* Provedores de IA
* Email
* WhatsApp
* Analytics
* Cloud storage

Não implementar integrações complexas no MVP.

---

# 59. Segurança e privacidade

Como os dados são locais nesta versão:

* Não enviar dados pessoais para servidores desnecessariamente.
* Não registrar dados privados em logs.
* Avisar quando informações forem enviadas para um serviço de IA externo.
* Separar claramente processamento local e processamento externo.
* Disponibilizar exportação e exclusão dos dados.

---

# 60. Design final

A aplicação deve parecer um SaaS moderno de carreira e inteligência artificial.

Características:

* Interface limpa.
* Muito espaço em branco.
* Cards sutis.
* Bordas discretas.
* Border radius moderado.
* Tipografia moderna.
* Lucide Icons.
* ShadCN UI.
* Azul celeste predominante.
* Azul escuro para texto.
* Branco como base.
* Vermelho apenas para alertas.

Evitar:

* Gradientes exagerados.
* Sombras excessivas.
* Animações desnecessárias.
* Excesso de cores.
* Elementos decorativos inúteis.
* Interface complexa.

---

# 61. Princípio central do produto

O MatchCV deve funcionar como um **assistente de preparação para candidaturas**.

Ele não deve simplesmente gerar um currículo genérico.

O fluxo deve ser contextual:

**Currículo-base + Vaga = Análise + Match + Sugestões + Currículo personalizado**

Cada currículo gerado deve estar relacionado a uma vaga específica.

---

# 62. Regra fundamental

A plataforma deve sempre preservar a autenticidade das informações do candidato.

Nunca incentivar o usuário a mentir.

Nunca criar experiência profissional fictícia.

Nunca inserir automaticamente uma habilidade que o usuário não confirmou.

Quando identificar uma lacuna, mostrar a lacuna.

Quando identificar uma oportunidade de melhoria, explicar como melhorar.

---

# 63. Critério de sucesso do MVP

Ao abrir o site pela primeira vez, o usuário deve conseguir utilizar o produto sem criar conta.

O fluxo completo deve funcionar assim:

**Abrir o MatchCV**

↓

**Criar ou importar currículo-base**

↓

**Adicionar uma vaga**

↓

**Analisar vaga**

↓

**Calcular compatibilidade**

↓

**Ver pontos compatíveis**

↓

**Ver lacunas**

↓

**Ver palavras-chave**

↓

**Ver análise ATS**

↓

**Gerar currículo personalizado**

↓

**Editar currículo**

↓

**Exportar PDF**

↓

**Registrar candidatura**

↓

**Acompanhar candidatura**

---

# 64. Instrução final para o Lovable

Implemente a aplicação completa seguindo todas as especificações acima.

Não criar autenticação.

Não criar cadastro.

Não criar login.

Não criar onboarding obrigatório.

O usuário deve entrar diretamente no produto e conseguir começar a trabalhar imediatamente.

Utilize armazenamento local no navegador no MVP, através de uma camada de persistência organizada e reutilizável.

Utilize **ShadCN UI como Design System oficial**.

Utilize:

**Azul celeste + Azul escuro + Branco + Vermelho para alertas.**

Priorize o seguinte fluxo como núcleo do produto:

**Currículo → Vaga → Match → Análise → ATS → Currículo personalizado → PDF → Candidatura**

A experiência deve ser simples, moderna, rápida e profissional.

O produto deve transmitir a sensação de uma ferramenta SaaS de carreira baseada em IA, sem exigir cadastro para começar.

A principal proposta de valor é:

**"Analise a vaga. Entenda seu match. Adapte seu currículo."**

```
---
## 3. Iterações com o Lovable

- **Ajuste solicitado:**  
  > Pedi para tirar a função de cadastro/login. Mudei as cores principais para tons de laranja. tambem pedi para gerar o curriculum em pdf.

- **Correção de erro:**  
  > De inicioo não estava navegando as telas corretamente, mas foi corrigido.

- **Resultado Final no Lovable:**  
  [MatchCV no Lovable](https://matchcv-curriculum.lovable.app//)

  ---
  ## 4. Prints das Interações

  <img width="1575" height="852" alt="image" src="https://github.com/user-attachments/assets/16c9bf90-c53d-4a43-85a6-95dd64ff8da1" />
  <img width="1575" height="852" alt="image" src="https://github.com/user-attachments/assets/651d2468-ff39-4504-b771-61bfc34b286d" />
  <img width="1575" height="852" alt="image" src="https://github.com/user-attachments/assets/20ff12b9-bf1d-461a-a737-205c094c9852" />
  <img width="1575" height="852" alt="image" src="https://github.com/user-attachments/assets/1bc094f6-8394-4387-86af-a422b3db4734" />
  <img width="1575" height="852" alt="image" src="https://github.com/user-attachments/assets/ed6a1f9d-2f12-4199-9980-740266f891e6" />


  ---
  ## 5. Finança AI – Resumo do Aplicativo

  ### Visão Geral
  O **MatchCV** é um aplicativo onde o usuário cadastra ou exporta seu curriculum e descreve ou linca a vaga desejada. O sistema faz uma analise e cruza os dados e por fim exibindo um relátorio de quantos por cento o curriculo esta de acordo com a vaga. Gera tambem informações de quais os pontos fortes e onde melhorar.

  O objetivo é fazer o usuário ter uma ideia de quanto ele se enquadra na vaga pretendida e onde pode melhorar




