# Desafio-de-projeto-Configurando-uma-inst-ncia-de-Banco-de-Dados-na-Azure

Para um desafio profissional completo de Configuração de uma Instância de Banco de Dados no Azure, vamos seguir um roteiro abrangente. Esse projeto abrange desde a criação da instância até a otimização do banco.


---

📌 Objetivo do Projeto

Configurar uma instância de Banco de Dados SQL no Microsoft Azure, aplicando boas práticas de segurança, escalabilidade e alta disponibilidade.


---

🔹 Passo 1 – Criar um Banco de Dados no Azure

1. Acesse o Azure Portal (portal.azure.com)


2. Criar um novo recurso → Pesquise SQL Database


3. Escolha o Grupo de Recursos (ou crie um novo)


4. Nomeie o Banco de Dados (Exemplo: db-ecommerce)


5. Crie um Servidor SQL

Nome do servidor: server-dio-diego

Localização: Escolha um próximo ao seu público

Autenticação: Autenticação do Azure AD + SQL



6. Escolha a camada de serviço

Básico (Testes/Desenvolvimento)

Standard ou Premium (Produção, com escalabilidade automática)



7. Configure a Rede

Ative Acesso Público e Firewall

Permita acesso do seu IP e do Azure Services



8. Criar Banco de Dados 🚀




---

🔹 Passo 2 – Configuração de Segurança

✅ Habilitar Autenticação Multifator (MFA) para acessos administrativos.
✅ Configurar Regras de Firewall
✅ Criar Usuários e Permissões
✅ Ativar Auditoria e Logs de Diagnóstico

-- Criar um usuário de leitura
CREATE USER leitor WITH PASSWORD = 'SenhaForte!';
ALTER ROLE db_datareader ADD MEMBER leitor;

-- Criar um usuário de escrita
CREATE USER escritor WITH PASSWORD = 'SenhaForte!';
ALTER ROLE db_datawriter ADD MEMBER escritor;


---

🔹 Passo 3 – Inserção de Dados e Indexação

1. Criar uma Tabela Exemplo



CREATE TABLE Produtos (
    ID INT IDENTITY PRIMARY KEY,
    Nome NVARCHAR(100) NOT NULL,
    Preco DECIMAL(10,2) NOT NULL,
    Estoque INT NOT NULL
);

2. Criar Índices para Performance



CREATE INDEX idx_produto_nome ON Produtos(Nome);

3. Inserir Dados



INSERT INTO Produtos (Nome, Preco, Estoque) VALUES 
('Notebook Gamer', 6500.00, 10),
('Teclado Mecânico', 350.00, 25),
('Monitor 144Hz', 1200.00, 15);


---

🔹 Passo 4 – Configurar Backup e Replicação

1. Ativar Backup Automático


2. Configurar Geo-Replicação (Alta Disponibilidade)


3. Simular um Restore para Testes



RESTORE DATABASE db-ecommerce FROM BACKUP;


---

🔹 Passo 5 – Monitoramento e Escalabilidade

✅ Configurar Monitoramento no Azure Monitor
✅ Ativar Alertas (CPU, Conexões, Armazenamento)
✅ Escalar Automaticamente com o Elastic Pool


---

🔹 Passo 6 – Teste de Conexão Local

1. Baixar Azure Data Studio ou SSMS


2. Conectar via String de Conexão



Server=tcp:server-dio-diego.database.windows.net,1433;
Database=db-ecommerce;
User ID=seu_usuario;
Password=sua_senha;
Encrypt=True;
TrustServerCertificate=False;
Connection Timeout=30;


---

🚀 Próximos Passos

✅ Subir esse projeto no GitHub, documentando cada etapa.
✅ Criar um Dashboard no Power BI com os dados do SQL.
✅ Fazer testes de carga e desempenho.

Esse projeto te dá um ótimo portfólio e conhecimento profissional avançado em Azure SQL! 🔥

