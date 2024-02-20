---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### ```./src/databases/:``` Lista de querys e metodos para banco de dados na aplicação.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### AppConfig | ```./src/databases/appconfig/query.tsx:```

Arquivo que armazena uma serie de funções com comandos em SQLite que compôem criação, modificação e consultas no banco de dados

Tabela principal:
```TypeScript
const table "app_config"
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Funções:

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```createTableQuery:``` Função responsável por criar a tabela principal.

Exemplo:
```TypeScript
createTableQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```insertDefaultsValuesQuery:``` Função responsável por definir as configurações padrões do app.

Exemplo:
```TypeScript
insertDefaultsValuesQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```buscarTodosQuery:``` Função responsável a buscar todos os produtos registrados no app.
```TypeScript
buscarTodosQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Produtos | ```./src/databases/produtos/query.tsx:```

Arquivo que armazena uma serie de funções com comandos em SQLite que compôem criação, modificação e consultas no banco de dados

Tabela principal:
```TypeScript
const table "produtos";
```

Tipagem principal:
```TypeScript
export interface IProdutoProps {
  id?: number;
  id_produto?: number;
  codigo_barras: string;
  nome: string;
  conferido?: number;
  quantidade?: number;
  preco_venda?: number;
  datahora_conferencia?: string;
}
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

#### Funções:

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```createTableQuery:``` Função responsável por criar a tabela principal.

Exemplo:
```TypeScript
createTableQuery();
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```dropTableQuery:``` Função responsável por deletar a tabela principal.

Exemplo:
```TypeScript
dropTableQuery();
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```deleteQuery:``` Função responsavel por apagar registros de produtos na tabela principal, recebe o parâmetro ```(produto: IProdutoProps)``` para executar.

Exemplo:
```TypeScript
import { IProdutoProps } from "./interfaces/InterfaceProduto";

const [produto, setProduto] = useState<IProdutoProps>({});

deleteQuery(produto);
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```deleteAllQuery:``` Função responsavel por apagar todos os registros de produtos da tabela principal.

Exemplo:
```TypeScript
deleteAllQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```deleteAllConferredsQuery:``` Função responsavel por apagar todos os registros de produtos que já foram conferidos,

Exemplo:
```TypeScript
deleteAllConferredsQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```insertQuery:``` Função responsavel por inserir novos registros de produtos, recebe o parâmetro ```(produto: IProdutoProps)``` para executar.

Exemplo:
```TypeScript
import { IProdutoProps } from "./interfaces/InterfaceProduto";

const [produto, setProduto] = useState<IProdutoProps>({});

insertQuery(produto);
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```buscarTodosQuery:```  Função responsavel por buscar todos os registros de produtos.

Exemplo:
```typeScript
buscarTodosQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```buscarPorIdOuCodigoBarrasQuery:``` Função responsavel por efetuar uma busca nos registros de produtos filtrando por ID ou Codigo de Barras, recebe o parâmetro ```(filtro: string)``` para executar.

Exemplo:
```typeScript
buscarPorIdOuCodigoBarrasQuery("filtro_teste");
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```buscarPorCodigoBarrasQuery:``` Função responsavel por efetuar uma busca nos registros de produtos filtrando por Codigo de Barras, recebe o parâmetro ```(filtro: string)``` para executar.

Exemplo:
```typeScript
buscarPorCodigoBarrasQuery("filtro_teste");
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```buscarConferidosQuery:``` Função responsavel por buscar apenas registros de produtos que já foram conferidos.

Exemplo:
```TypeScript
buscarConferidosQuery()
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```adicionarConferenciaQuery:``` Função responsavel por classificar o registro do produto como conferido, recebe os parâmetros ```id: number | string, quantidade: number``` para executar.

Exemplo:
```TypeScript
adicionarConferenciaQuery(1, 5);
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

```removeConferenciaQuery:``` Função responsavel por remover classificação de conferido do registro do produto, recebe os parâmetros ```id: number | string``` para executar.

Exemplo:
```TypeScript
removeConferenciaQuery(1);
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------


```removeTodasConferenciasQuery:``` Função responsavel por remover todas as classificações de conferido de todos os registros de produtos.

Exemplo:
```TypeScript
removeTodasConferenciasQuery();
```

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

