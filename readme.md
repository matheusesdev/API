Documentação da API de Filmes.

Esta API permite gerenciar uma lista de filmes, possibilitando operações de leitura, adição, atualização e remoção de filmes (CRUD). Desenvolvida usando Express.JS.

##Endpoints##

1. GET /filmes: Retorna a lista completa de filmes em formato JSON. = http://localhost:3000/filmes
2. GET /filmes/:id: Recupera um filme pelo seu id. Se o filme for encontrado, retorna o objeto do filme; caso contrário, retorna um status 404 com a mensagem "Filme não encontrado". - http://localhost:3000/filmes/2
3. GET /filmes/nome/:titulo: Busca filmes pelo título. Converte o termo de busca para minúsculas para comparação sem distinção de maiúsculas e minúsculas. Se filmes correspondentes ao título forem encontrados, retorna-os; caso contrário, retorna um status 404 com a mensagem "Nenhum filme encontrado com esse título". http://localhost:3000/filmes/nome/parasita
4. POST /filmes: Adiciona um novo filme à lista. Verifica se um filme com o mesmo título e ano de lançamento já existe. Se existir, retorna um status 400 com a mensagem "Este filme já foi adicionado". Caso contrário, atribui um novo id ao filme, adiciona-o à lista e retorna um status 201 com uma mensagem de sucesso e o filme adicionado.
5. PUT /filmes/:id: Atualiza um filme existente pelo seu id. Se o filme for encontrado, mescla os dados existentes do filme com os novos dados do corpo da requisição e retorna uma mensagem de sucesso. Se o filme não for encontrado, retorna um status 404 com a mensagem "Filme não encontrado".
6. DELETE /filmes/:id: Deleta um filme pelo seu id. Se o filme for encontrado, remove-o da lista e retorna uma mensagem de sucesso. Se o filme não for encontrado, retorna um status 404 com a mensagem "Filme não encontrado".

Finalmente, o servidor começa a escutar na porta especificada e exibe uma mensagem indicando que a API está rodando.

Tecnologias Utilizadas:
Node.js: Ambiente de execução JavaScript.
Express.js: Framework para criar APIs RESTful.
CORS: Middleware para permitir requisições de outras origens.

Informações SOBRE O CÓDIGO JS:

1. O código JavaScript fornecido está embutido dentro de uma tag de script HTML e é projetado para buscar e exibir dados de filmes de uma API. A constante `API_URL` contém a URL do endpoint para buscar os dados dos filmes.

2. A função `buscarFilmes` é uma função assíncrona que recupera a entrada do usuário a partir de um elemento de entrada HTML com o ID `searchInput`. Ela verifica se a entrada é válida (não indefinida, nula ou vazia). Se a entrada for inválida, a função retorna cedo sem fazer uma requisição fetch. Se a entrada for válida, ela converte a entrada para minúsculas e remove qualquer espaço em branco.

3. A função então faz uma requisição fetch para o `API_URL` para obter os dados dos filmes. Se a resposta não for OK, ela lança um erro. Após buscar os dados com sucesso, ela filtra os filmes com base em se o título do filme inclui a entrada de busca. Os filmes filtrados são então passados para a função `exibirFilmes` para exibição.

4. A função `exibirFilmes` recebe um array de objetos de filmes e os exibe na página web. Primeiro, ela limpa qualquer conteúdo existente no elemento `movieList`. Se nenhum filme for encontrado, ela exibe uma mensagem indicando que nenhum filme foi encontrado. Para cada filme, ela cria um elemento de cartão contendo o pôster do filme, título, idioma, duração, atores principais, ano de lançamento, avaliação, sinopse e ícones das plataformas. Esses cartões são adicionados ao elemento `movieList`.

5. A função `getPlatformIcon` retorna uma string HTML contendo uma tag de âncora com uma imagem do ícone da plataforma. Ela recebe um nome de plataforma como entrada, determina a URL do ícone apropriado e o link com base no nome da plataforma, e retorna a string HTML. Se o nome da plataforma não for reconhecido, ela retorna um ícone de espaço reservado com um link para `#`.

Endpoints:
Listar todos os filmes - http://localhost:3000/filmes
Pesquisar filme pelo id - http://localhost:3000/filmes/2
Pesquisar pelo “nome” = http://localhost:3000/filmes/nome/parasita
Incluir objeto novo = método post http://localhost:3000/filmes (colar o script do filme que está no whatsapp)
Alterar um objeto = metodo put http://localhost:3000 (alterar alguma informação do filme, colocar ID ou nome do filme.)
Deletar um objeto = metodo delete http://localhost:3000/filmes

1. Parasita
2. A vida é bela
3. O fabuloso destino de Amélie Poualain
4. Cidade de Deus
5. O Labirinto do Fauno
6. O Artista
7. Intocáveis
8. Rashomon
9. Roma
10. O Tigre e o Dragão
