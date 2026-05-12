# Prompt Codex — ClientHub

Este arquivo contém o prompt principal usado para orientar a implementação do projeto no Codex.

## Produto

ClientHub é um SaaS para freelancers, desenvolvedores, designers, pequenas agências e prestadores digitais acompanharem projetos, etapas, tarefas, aprovações e entregas com seus clientes.

## Stack obrigatória

- Laravel 13
- Vue.js 3
- TypeScript
- MySQL
- Tailwind CSS
- Vite
- Inertia.js

## Regras principais

- Seguir SOLID e Clean Code.
- Usar Controllers finos.
- Usar Services para regras de negócio.
- Usar Form Requests para validação.
- Usar Policies para autorização.
- Usar Enums para status de projetos, etapas, tarefas e roles.
- Criar painel admin.
- Criar CRUD de planos.
- Criar pelo menos um Plano Gratuito.
- Criar SEO básico.
- Criar `public/robots.txt`.
- Criar `public/sitemap.xml`.
- Criar manual em Markdown.
- Preparar deploy para VPS Hostinger KVM 1 com CloudPanel, Nginx, PHP-FPM, MySQL e Cloudflare.

## Prompt completo

Você é um arquiteto de software especialista em Laravel 13, Vue.js 3, TypeScript, MySQL, SaaS B2B simples, SOLID e Clean Code.

Crie um SaaS chamado "ClienteHub", um portal do cliente para freelancers, desenvolvedores, designers, pequenas agências e prestadores digitais acompanharem projetos, etapas, aprovações e entregas.

Stack obrigatória:
- Laravel 13
- Vue.js 3
- TypeScript
- MySQL
- Tailwind CSS
- Vite
- Inertia.js com Vue 3
- Autenticação compatível com Laravel 13

Objetivo:
Permitir que profissionais organizem projetos e deem aos clientes uma área simples de acompanhamento.

Personas:
1. Desenvolvedor freelancer.
2. Designer freelancer.
3. Pequena agência.
4. Social media.
5. Consultor que entrega projetos por etapas.

Funcionalidades do usuário:
- Cadastro/login.
- Dashboard:
  - projetos ativos;
  - etapas aguardando aprovação;
  - tarefas abertas;
  - clientes ativos;
  - limite do plano.
- CRUD de clientes.
- CRUD de projetos.
- Projeto deve conter:
  - cliente;
  - nome;
  - descrição;
  - data de início;
  - prazo;
  - status;
  - progresso;
  - valor opcional;
  - observações internas.
- Etapas do projeto:
  - título;
  - descrição;
  - ordem;
  - status;
  - prazo;
  - aprovação do cliente.
- Tarefas:
  - título;
  - descrição;
  - status;
  - responsável;
  - prazo.
- Comentários por projeto/etapa.
- Upload de arquivos.
- Link público ou acesso simplificado para cliente visualizar projeto.
- Cliente pode aprovar etapa.
- Histórico de aprovações.
- Status:
  - planejamento;
  - em andamento;
  - aguardando cliente;
  - em revisão;
  - concluído;
  - cancelado.
- Cores configuráveis por variáveis.

Painel admin:
- Role admin.
- CRUD de planos.
- CRUD de usuários.
- Admin altera plano manualmente.
- Configurações globais:
  - nome;
  - domínio;
  - e-mail;
  - cores padrão;
  - SEO padrão;
  - limites.
- Relatórios:
  - usuários por plano;
  - projetos criados;
  - arquivos armazenados;
  - usuários ativos.

Planos:
- Gratuito:
  - até 2 projetos ativos;
  - até 3 clientes;
  - sem upload ou upload limitado.
- Pro:
  - até 20 projetos ativos;
  - clientes ilimitados;
  - upload de arquivos.
- Plus:
  - projetos ilimitados;
  - personalização visual;
  - portal com marca do usuário.

SEO:
- Criar Home, Recursos, Preços, Termos e Privacidade.
- Implementar metatags, canonical, Open Graph, Twitter Card.
- Schema.org SoftwareApplication.
- public/robots.txt.
- public/sitemap.xml.
- Não indexar projetos, arquivos, área do cliente, dashboard ou admin.

Arquitetura:
- Controllers finos.
- Services:
  - ProjectService;
  - StageApprovalService;
  - PlanLimitService;
  - FileUploadService.
- Form Requests.
- Policies.
- Enums:
  - ProjectStatus;
  - StageStatus;
  - TaskStatus;
  - UserRole.
- Migrations com foreign keys.
- Seeders para admin, planos e configurações.
- Factories.
- Testes:
  - criação de projeto;
  - limite do plano gratuito;
  - aprovação de etapa;
  - usuário não acessa projetos de outro usuário;
  - admin altera plano.

Entidades:
- User
- Plan
- UserPlan
- Customer
- Project
- ProjectStage
- ProjectTask
- ProjectComment
- ProjectFile
- StageApproval
- AppSetting

Manual:
- Criar docs/MANUAL.md explicando uso pelo profissional e pelo admin.
- Criar README.md técnico.
- Criar docs/DEPLOY.md para VPS Hostinger KVM 1.

Não implementar cobrança online agora. O admin gerencia planos manualmente. Preparar estrutura para futura integração.


### Regras globais do projeto:

1. Stack obrigatória:
   - Laravel 13
   - Vue.js 3
   - TypeScript
   - MySQL
   - Tailwind CSS
   - Vite

2. Arquitetura:
   - Seguir SOLID, Clean Code e separação de responsabilidades.
   - Controllers devem ser finos.
   - Usar Form Requests para validação.
   - Usar Policies para autorização.
   - Usar Services/Actions para regras de negócio.
   - Usar Enums para status, roles e tipos fixos.
   - Usar migrations com foreign keys, índices e constraints.
   - Usar seeders para dados iniciais.
   - Usar factories e testes mínimos.

3. SaaS:
   - Todo projeto deve ter planos.
   - Deve existir no mínimo Plano Gratuito.
   - Planos devem ser configuráveis pelo painel admin.
   - Admin deve poder alterar plano do usuário manualmente.
   - Não implementar pagamento online no MVP.
   - Preparar estrutura para futura integração com cobrança.

4. Admin:
   - Criar role admin.
   - Criar painel admin protegido.
   - Admin deve gerenciar usuários, planos e configurações globais.
   - Admin deve visualizar relatórios básicos.

5. SEO:
   - Criar páginas públicas:
     - Home
     - Recursos
     - Preços
     - Termos de Uso
     - Política de Privacidade
   - Implementar title, meta description, canonical, Open Graph e Twitter Card.
   - Criar Schema.org SoftwareApplication quando aplicável.
   - Criar public/robots.txt.
   - Criar public/sitemap.xml.
   - Não indexar rotas autenticadas, admin, dashboard ou dados privados.

6. Front-end:
   - Usar Vue 3 com TypeScript.
   - Componentizar telas e elementos reutilizáveis.
   - Usar Tailwind CSS.
   - Cores principais devem ser configuráveis via variáveis CSS.
   - Evitar cores hardcoded espalhadas no projeto.
   - Criar layout público, layout autenticado e layout admin.

7. Deploy:
   - Preparar para VPS KVM 1 da Hostinger com Nginx, PHP-FPM, MySQL e Node.
   - Criar docs/DEPLOY.md.
   - Documentar:
     - composer install
     - npm install
     - npm run build
     - php artisan migrate --seed
     - php artisan storage:link
     - permissões
     - configuração .env
     - cache de config, routes e views

8. Documentação:
   - Criar / Atualizar README.md técnico.
   - Criar / Atualizar docs/MANUAL.md para uso do sistema.
   - Criar / Atualizar docs/ROADMAP.md com melhorias futuras.
   - Criar / Atualizar docs/DEPLOY.md.

9. Segurança:
   - Isolar dados por usuário.
   - Nunca permitir que um usuário acesse dados de outro.
   - Validar permissões via Policies.
   - Proteger rotas admin.
   - Não expor dados privados no sitemap.
   - Não indexar páginas privadas.

10. Qualidade:
   - Criar testes mínimos para regras principais.
   - Evitar overengineering.
   - Priorizar MVP funcional, limpo, simples e evolutivo.