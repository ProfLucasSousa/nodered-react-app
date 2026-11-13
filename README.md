# Node-RED React App

Aplicação React para visualizar e remover dados recebidos por uma API serverless conectada a um banco MySQL. O projeto pode ser usado com fluxos Node-RED que enviam pares de atributo e valor para a rota da aplicação.

## Tecnologias

- React 18
- TypeScript
- Vite
- Vercel Functions
- MySQL
- Lucide React

## Funcionalidades

- Consulta dos registros armazenados.
- Atualização manual da listagem.
- Exclusão de registros.
- Tratamento de carregamento e erro.
- Endpoint serverless para leitura, gravação e exclusão.

## Configuração

Copie o arquivo de exemplo:

```bash
cp .env.example .env
```

Configure:

```env
DB_HOST=localhost
DB_PORT=3306
DB_USER=usuario
DB_PASSWORD=senha
DB_NAME=banco
```

Na Vercel, cadastre as mesmas variáveis nas configurações do projeto.

A API espera uma tabela semelhante a:

```sql
CREATE TABLE dados (
  id INT AUTO_INCREMENT PRIMARY KEY,
  atributo VARCHAR(255) NOT NULL,
  valor TEXT
);
```

## Como executar

```bash
npm install
npm run dev
```

O comando acima inicia o front-end. Para testar também a função em `api/receiveData.tsx` localmente, use o ambiente de desenvolvimento da Vercel:

```bash
npx vercel dev
```

## API

| Método | Rota | Ação |
| --- | --- | --- |
| `GET` | `/api/receiveData` | Lista os registros |
| `POST` | `/api/receiveData` | Grava os pares enviados no corpo |
| `DELETE` | `/api/receiveData?id={id}` | Exclui um registro |

## Scripts

```bash
npm run dev
npm run build
npm run lint
npm run preview
```
