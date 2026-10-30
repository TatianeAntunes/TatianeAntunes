<div align="center">

# Olá, eu sou a Tatiane 👋

### Desenvolvedora Front-end · React · JavaScript · TypeScript

Construo interfaces claras e rápidas, ligadas a dados reais, pagamentos e regras de negócio.
Atualmente em busca da minha próxima oportunidade como **Desenvolvedora Front-end**.

[![Portfólio](https://img.shields.io/badge/Portf%C3%B3lio-111827?style=for-the-badge&logo=githubpages&logoColor=white)](https://tatianeantunes.github.io/portfolio)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tatiane-antunes-devfront-end)
[![E-mail](https://img.shields.io/badge/E--mail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:antunes.tatiane.s@gmail.com)

</div>

---

## 🚀 Projeto em destaque: AgendaPro

> **De agosto a outubro de 2026 me dediquei a construir o AgendaPro, um SaaS completo de agendamento.**
> O código está em um repositório privado porque é um produto comercial. Abaixo está o que
> eu construí e as decisões técnicas por trás dele. Posso mostrar o código e fazer uma demonstração
> ao vivo em uma conversa.

**O problema:** barbeiros, cabeleireiros, manicures e profissionais de estética perdem tempo e
dinheiro com horários bagunçados e clientes que esquecem de aparecer.

**A solução:** uma agenda simples o bastante para usar entre um corte e outro. O cliente
confirma a presença pelo WhatsApp com um clique, e o profissional vê o dia inteiro em uma tela só.

🔗 **[Ver o AgendaPro no ar](https://agendapro-com-br.lovable.app)**

### O que o produto faz

| | |
|---|---|
| 📅 **Agenda por dia** | Todos os horários do dia em uma tela, com status (aguardando, confirmado, concluído, cancelado) e aviso de atendimentos atrasados |
| 💬 **Confirmação por WhatsApp** | Um clique abre a conversa com a mensagem pronta, com nome, serviço e horário |
| 👥 **Clientes** | Cadastro com telefone, e-mail e observações |
| ✂️ **Serviços** | Preço e duração de cada serviço, que alimentam a agenda |
| 📊 **Dashboard** | Resumo do dia: horários, confirmados, pendentes e clientes dos próximos 7 dias |
| 💳 **Assinatura** | 14 dias de teste grátis e plano Pro mensal via Stripe |
| ⭐ **Feedback** | Coleta de nota e comentário dos usuários, com aviso por e-mail para mim |

### Desafios técnicos que resolvi

- **Sem horários duplicados.** Além de validar no front-end, o banco de dados impede sobreposição
  de atendimentos com uma *exclusion constraint* no PostgreSQL. Se duas pessoas tentarem marcar o
  mesmo horário ao mesmo tempo, o banco recusa e a interface mostra uma mensagem clara.
- **Multiempresa e segurança.** Cada negócio só enxerga os próprios dados, garantido por
  *Row Level Security* no Supabase, com papéis de dono e funcionário. A segurança fica no banco,
  não depende só do código da interface.
- **Pagamentos de ponta a ponta.** Integração com Stripe (Checkout, portal de cobrança e webhook com
  validação de assinatura) que mantém o estado da assinatura sincronizado. Quando a assinatura vence,
  o app libera só a leitura e bloqueia a escrita, com mensagem amigável.
- **Cache e performance.** TanStack Query com invalidação seletiva e reaproveitamento da empresa do
  usuário durante a sessão, evitando consultas repetidas.
- **Autenticação robusta.** Login com e-mail/senha e Google. Corrigi condições de corrida no
  redirecionamento pós-login e no retorno do OAuth, testando os dois fluxos separadamente.
- **Telefones brasileiros.** Normalização e formatação de DDD e DDI para gerar links `wa.me`
  corretos, inclusive o caso do DDD 55 (RS), que se confunde com o código do país.
- **LGPD.** Termos de Uso e Política de Privacidade versionados, com aceite registrado no banco e
  novo aceite pedido quando os documentos mudam.
- **E-mails transacionais** com templates em React Email (confirmação, recuperação de senha, convite).

### Stack do AgendaPro

![React](https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![TanStack](https://img.shields.io/badge/TanStack_Start_·_Router_·_Query-FF4154?style=flat-square&logo=reactquery&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui_·_Radix-000000?style=flat-square&logo=shadcnui&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase_·_PostgreSQL-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![Zod](https://img.shields.io/badge/Zod_·_React_Hook_Form-3E67B1?style=flat-square&logo=zod&logoColor=white)
![Lovable](https://img.shields.io/badge/Lovable-FF4F8B?style=flat-square)

Interface com **TanStack Start (SSR)**, **React 19** e **TypeScript**, estilizada com **Tailwind CSS 4**
e componentes acessíveis do **Radix/shadcn**. Validação de formulários com **Zod** e
**React Hook Form**, gráficos com **Recharts** e datas com **date-fns**. Backend com **Supabase**
(PostgreSQL, autenticação e RLS) e pagamentos com **Stripe**.

### Como o projeto é organizado

```
src/
  routes/          páginas e rotas por arquivo (área logada, login, termos, webhook do Stripe)
  components/      componentes do app e biblioteca de UI reutilizável
  lib/             regras de negócio: agenda, WhatsApp, Stripe, termos, e-mails
  integrations/    clientes do Supabase
supabase/migrations/   esquema do banco, políticas RLS e funções (histórico versionado)
```

---

## 🛠️ Tecnologias

**Linguagens e front-end:** HTML · CSS · JavaScript · TypeScript · React
**Estilo e UI:** Tailwind CSS · shadcn/ui · Radix UI
**Dados e back-end:** Supabase · PostgreSQL · TanStack Query · Zod
**Pagamentos e integrações:** Stripe · WhatsApp (wa.me) · e-mail transacional
**Ferramentas:** Git · GitHub · Vite · ESLint · Prettier · Bun/npm

## 🎯 Em que estou focada

- Aprofundar meu domínio de React e TypeScript
- Construir interfaces acessíveis, responsivas e com boa experiência de uso
- Escrever código legível, com validação e tratamento de erros pensados desde o início

## 📫 Vamos conversar?

Se você tem uma vaga de Front-end ou quer ver o AgendaPro funcionando por dentro, me chame:

- 🌐 [Portfólio](https://tatianeantunes.github.io/portfolio)
- 💼 [LinkedIn](https://www.linkedin.com/in/tatiane-antunes-devfront-end)
- ✉️ [antunes.tatiane.s@gmail.com](mailto:antunes.tatiane.s@gmail.com)
