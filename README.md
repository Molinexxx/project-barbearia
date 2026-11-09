# BarberPro SaaS em PHP

Sistema SaaS para barbearias desenvolvido em PHP com estrutura MVC simples, autenticação por sessão e banco MySQL.

## Funcionalidades

- cadastro e login de barbearias
- dashboard com indicadores operacionais
- gestão de clientes
- gestão de serviços
- gestão de usuários da equipe
- controle de permissões por perfil
- cadastro, edição e exclusão de agendamentos
- atualização de status dos atendimentos
- validação de conflito de horários
- agenda geral e minha agenda
- configuração de horário de funcionamento
- cadastro de pausas e indisponibilidade de profissionais
- isolamento por `barbearia_id`

## Perfis de acesso

- `admin`: acesso total ao sistema
- `recepcao`: agenda, clientes, serviços e disponibilidade
- `barbeiro`: visualização de clientes e acesso apenas à própria agenda

## Tecnologias

- PHP 8.0 ou superior
- MySQL
- PDO
- Bootstrap
- CSS customizado

## Estrutura do projeto

- `barbearia/config`: conexão com banco e autenticação
- `barbearia/controllers`: regras de negócio e actions
- `barbearia/models`: acesso ao banco
- `barbearia/views`: interface do sistema
- `barbearia/css`: estilos
- `barbearia.sql`: script de criação do banco

## Como executar

1. Importe o arquivo `barbearia.sql` no MySQL.
2. Para uma execução local, ajuste a conexão em [`barbearia/config/database.php`](barbearia/config/database.php) e mantenha as credenciais fora do Git.
3. Com PHP 8.0 ou superior e a extensão `pdo_mysql` habilitada, execute `php -S localhost:8000` na raiz do repositório. O painel usa a expressão `match`, disponível a partir do PHP 8.0.
4. Abra a [tela de login](http://localhost:8000/barbearia/views/auth/login.php). Para criar uma barbearia e seu usuário inicial, use a [tela de cadastro](http://localhost:8000/barbearia/views/auth/register.php).

## Recursos implementados

- multi-barbearia com separação por empresa
- dashboard adaptado por perfil
- controle de equipe
- validação de expediente e pausas na agenda
- restrição de acesso por tipo de usuário
- manutenção completa de agendamentos

## Indicadores do painel

O painel mostra contagens de agendamentos do dia por status, com recorte por profissional na visão do barbeiro. O cadastro de serviços registra preços. O painel ainda não soma esses preços como faturamento e o controle de pagamentos está previsto como evolução.

## Próximos passos previstos

- módulo financeiro
- comandas e pagamentos
- relatórios
- histórico completo de clientes
- melhorias de segurança e deploy
