# Pet Shop Scheduler

Aplicação de agenda para pet shop construída com **Next.js 15**, **React 19**, **TypeScript** e **PostgreSQL**.

## Descrição

Este projeto permite gerenciar agendamentos de atendimentos para um pet shop. A aplicação exibe os agendamentos do dia selecionado, organiza horários por períodos e fornece um formulário para criar novos compromissos.

## Estrutura principal

- `src/app` - páginas e layout da aplicação Next.js.
- `src/components` - componentes de interface como formulário de agendamento, seletor de data e seções de período.
- `src/lib/prisma.ts` - cliente Prisma configurado com `@prisma/adapter-pg`.
- `prisma/schema.prisma` - modelo de dados para `Appointment`.
- `docker-compose.yml` - serviço PostgreSQL local para desenvolvimento.

## Tecnologias

- Next.js 15
- React 19
- TypeScript
- Tailwind CSS 4
- Prisma ORM 6
- PostgreSQL
- Radix UI
- React Hook Form
- Zod
- date-fns

## Banco de dados

A aplicação usa PostgreSQL com Prisma. O modelo principal é `Appointment`:

- `id` - identificador único
- `tutorName` - nome do tutor
- `petName` - nome do pet
- `phone` - telefone de contato
- `description` - descrição do atendimento
- `scheduleAt` - data e hora do agendamento

## Executando localmente

1. Instale dependências:

```bash
npm install
```

2. Inicie o banco de dados PostgreSQL com Docker:

```bash
docker compose up -d
```

3. Configure a variável de ambiente `DATABASE_URL` em `.env` ou use `.env.example` como referência:

```env
DATABASE_URL="postgresql://docker:docker@localhost:5432/petshop"
```

4. Gere o cliente Prisma (se necessário):

```bash
npx prisma generate
```

5. Execute a aplicação:

```bash
npm run dev
```

6. Acesse em:

```text
http://localhost:3000
```

## Scripts

- `npm run dev` - executa o servidor de desenvolvimento.
- `npm run build` - cria a build de produção.
- `npm run start` - inicia o servidor de produção.
- `npm run lint` - executa o ESLint.
- `npm run format` - formata o código com Prettier.
- `npm run validate:typecheck` - valida tipos com TypeScript.

## Notas

- O banco de dados é persistido no volume `./pgdata` definido em `docker-compose.yml`.
- O serviço PostgreSQL expõe a porta `5432`.
- O cliente Prisma é inicializado em `src/lib/prisma.ts` usando `DATABASE_URL`.

## Contato

Este repositório é um projeto de estudo do curso da Rocketseat e serve como um exemplo de agenda com Next.js, Prisma e PostgreSQL.
