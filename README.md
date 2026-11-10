# 🎓 MonitorIA | Gestão de Monitoria Acadêmica

> Organize horários entre monitores e alunos com facilidade.

**MonitorIA** é um sistema web de gestão de monitoria acadêmica, criado para a **UNICID**. Ele permite que a coordenação cadastre monitores e suas disponibilidades, que alunos solicitem sessões de monitoria e que todo o fluxo (solicitação → confirmação → conclusão) seja acompanhado em um dashboard, em uma grade semanal e em um histórico exportável.

O projeto é uma aplicação **front-end pura** (HTML, CSS e JavaScript), sem frameworks e sem back-end. Os dados são salvos no `localStorage` do navegador.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Sem dependências](https://img.shields.io/badge/depend%C3%AAncias-nenhuma-success?style=flat)

---

## 📸 Preview

> Adicione aqui capturas de tela do projeto (ex.: `docs/dashboard.png`, `docs/grade.png`).

---

## ✨ Funcionalidades

### 📊 Dashboard
- Cards de métricas: **monitores ativos**, **sessões agendadas**, **aguardando confirmação** e **sessões concluídas**.
- Lista das **próximas sessões** (as 5 mais recentes pendentes ou confirmadas).
- **Status dos monitores** cadastrados.
- **Sino de notificações** com contador de sessões pendentes.

### 👥 Monitores
- Cadastro, edição e remoção de monitores (com confirmação em dois cliques para excluir).
- Dados do monitor: nome, RA, disciplina, e-mail, local de atendimento e vagas por sessão.
- **Grade de disponibilidade semanal** interativa (segunda a sábado, das 08h às 20h) para marcar os horários.
- Busca por nome ou disciplina.

### 📅 Agendamento
- Formulário de solicitação com nome e RA do aluno, monitor, **horário (carregado conforme a disponibilidade do monitor selecionado)**, dúvida/assunto e modalidade (**Presencial** ou **Online**).
- Painel de sessões solicitadas com filtros: **Todas**, **Pendentes** e **Confirmadas**.
- Ações por sessão: **Confirmar**, **Concluir** e **Cancelar**.

### 🗓️ Grade Semanal
- Visão em tabela de dias × horários com a disponibilidade de cada monitor.
- Cores diferentes para horários **disponíveis**, **pendentes** e **confirmados**.
- Filtro por monitor.

### 🕘 Histórico
- Tabela com todas as sessões, ordenadas da mais recente para a mais antiga.
- Busca por aluno, monitor ou disciplina e filtro por status (pendente, confirmada, concluída, cancelada).
- Confirmação ou cancelamento rápido de sessões pendentes.
- **Exportação para CSV** (compatível com Excel, com codificação UTF-8).

### 🧩 Interface
- Layout com **sidebar** e barra superior com a data atual.
- Menu lateral recolhível para telas pequenas.
- **Notificações toast** para feedback das ações.
- Tipografia: [Inter](https://fonts.google.com/specimen/Inter) e [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono).

---

## 🔄 Ciclo de vida de uma sessão

```
 Aluno solicita          Coordenação confirma        Sessão realizada
┌─────────────┐        ┌────────────────────┐        ┌──────────────┐
│  PENDENTE   │ ─────▶ │     CONFIRMADA     │ ─────▶ │   CONCLUÍDA  │
└─────────────┘        └────────────────────┘        └──────────────┘
       │                         │
       └────────────┬────────────┘
                    ▼
              ┌────────────┐
              │ CANCELADA  │
              └────────────┘
```

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura semântica, modais acessíveis (`role="dialog"`) |
| CSS3 | Estilização, layout responsivo e componentes |
| JavaScript (ES6+) | Lógica da aplicação, renderização dinâmica e delegação de eventos |
| `localStorage` | Persistência de monitores e sessões |
| Google Fonts | Inter e JetBrains Mono |

---

## 🚀 Como executar

Não é necessário instalar nada.

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/monitoria.git

# 2. Acesse a pasta
cd monitoria

# 3. Abra o index.html no navegador
# (dois cliques no arquivo ou use uma extensão como Live Server)
```

> A conexão com a internet é necessária apenas para carregar as fontes do Google Fonts.

---

## 📁 Estrutura do projeto

```
monitoria/
├── index.html   # Estrutura das telas, modais e formulários
├── style.css    # Estilos da interface
├── app.js       # Lógica, estado e renderização
└── README.md
```

---

## 💾 Dados no localStorage

| Chave | Conteúdo |
|---|---|
| `monitoria_monitores` | Lista de monitores e suas disponibilidades |
| `monitoria_sessoes` | Lista de sessões de monitoria e seus status |

Para limpar todos os dados, apague essas chaves nas ferramentas de desenvolvedor do navegador (Application → Local Storage).

---

## ⚠️ Limitações conhecidas

Por ser um projeto sem back-end, vale ter em mente:

- Os dados ficam apenas no navegador de quem usa; não há compartilhamento entre dispositivos.
- Não há login: o perfil "Admin / Coordenador" exibido na sidebar é apenas visual.
- O sistema **não impede que mais de um aluno solicite o mesmo horário** de um monitor, e o campo "vagas por sessão" ainda não é validado.
- A navegação de semanas na Grade Semanal é apenas **cosmética** (a grade mostra sempre a disponibilidade semanal recorrente).
- Os textos digitados são renderizados via `innerHTML` sem sanitização. Antes de levar a produção, é recomendável escapar esses valores.

---

## 🗺️ Próximos passos

- [ ] Back-end com API e banco de dados
- [ ] Autenticação com perfis (aluno, monitor e coordenador)
- [ ] Bloqueio de horários já ocupados e controle de vagas
- [ ] Grade semanal com datas reais
- [ ] Notificações por e-mail para alunos e monitores
- [ ] Sanitização de entradas e escape de CSV
- [ ] Relatórios e gráficos de frequência por disciplina

---

## 📄 Licença

Distribuído sob a licença MIT. Veja o arquivo `LICENSE` para mais informações.

---

<p align="center">Feito com 💙 para facilitar a vida de quem ensina e de quem aprende.</p>
