    *Modúlo 3 Capitulo 21*
- Aula 01: Ainda podemos usar tabelas em HTML?
   ! Não pode usar tabela para criar a estrutura do site. 
     Antigamente as pessoas criavam sites com tabelas (HTML 4), com a evolução do HTML, e as CSS da para criar os sites sem precisar usar uma tabela. Sites criados em tabelas não muito duros e dificeis de posicionar as coisas. As tabelas são ruins para criar layout the site, e são boas para organização de dados. 

- Aula 02: Sua primeira tabela em HTML
    Use a tag <table> para delimitar a tabela.
    *Hieraquia das tabelas em HTML (simples)* 
        TABLE >
            TABLE ROW <tr> (linha de tabelas) >
                TABLE HEADER (cabeçalho de tabela)
                    TABLE DATA <td> (dado de tabela ) é cada dado da tabela
    Para fazer as linhas da tabela, no CSS é apenas criar uma border solid para cada <td>
    Para você deixar as linhas da tabela juntas no table use o 
        border-collapse: collapse;
    *OBS*
        O W3C na HTML5 ele coloca como opcional o feichamento das tedes *td* e *tr* 
        Se a hirarquia da tabela não for obedeciada os dados vão aparecer antes ou depois da tabela.
        Você pode personalizar cada linda ou dado dando uma class para eles e personalizando eles no CSS

- Aula 03: Alinhando o conteúdo em tabelas
     text-align: center; /*Alinhamento Horizontal*/
            vertical-align: top; /*Alinhamento vertical*/

- Aula 04: Aprendendo a trabalhar com tabelas grandes
    Até agora vimos tabela simples, agora vamos ver uma tabela grande 
    *Anatomia para tabelas grandes*
        Table
            caption *legenda da tabela* 
            thead // não obrigatorio
                <tr>,<td>,<th>
            tbody 
                <tr>,<td>,<th>
            tfoot // não obrigatorio
                <tr>,<td>,<th>

- Aula 05: Caption e Escopo de titúulos em tabelas
    *Em que momento usar td ou th?* 
        Pense sempre se é um dado ou apenas um titúlo, sempre que for um dado é <td>, sempre que for titúlos é <th>
    Para deixar claro sobre qual para o HTML se o titúlo é de coluna ou de linha, para fazer isso use o scope
    <th scope='col'> = Para coluna ou 
    <th scope='row'> = Para linha
        EX:
            <th scope="row">Total de Habitantes</th>
            <th scope="col">Estado</th>
            <th scope="col">População</th>
    Isso é importante para que os mecanismos de busca, como o Google, consiga analizar os dados coerentes. 

- Aula 06: Efeito Zebrado com HTML e CSS
    Para colocar o efeito zebraico na sua tabela: 
    tbody > tr:nth-child(2n) {
            background-color: lightgray;
        } *Esse 2n significa que de dois em dois vai colocar o background cinza*
        Você tambem pode colocar como par ou impar no lugar do 2n (ODD (impar), our even(par))
    CASO QUISER DEFINIR AS DUAS CORES
    tbody > tr:nth-child(odd) {
        background-color: white;

    tbody > tr:nth-child(even) {
            background-color: lightgray;

- Aula 07: Cabeçalho fixo em tabelas grandes
    Primeiro a tabela precisa ter um posicionamento relativo! Ai é só fazer o seguinte: 
         thead > tr > th { 
            position: sticky;
            top: -1px;
            background-color: #8a8a8a;
        }

- Aula 08: Mesclagem de Células 
    Fazer uma célula ocupar duas COLUNAS
        <td colspan="2">B</td>       
    Fazer uma célula ocupar duas LINHAS
        <td rowspan="3">D</td>

- Aula 09: Desafios (Parte 1)
    Fazendo o desafio 13 do material

- Aula 10: Exemplo de Tabela Completa
    Não esqueça o scopo!!!! TH sempre tem escopo

- Aula 11: Escopos de Grupos
    Quando for dar o scope do grupo de células use o group: *fazer desenho para mostrar*
    <th scope='colgrupo'> Quando é um grupo de colunas 
     <th scope="rowgroup"> Quando é um grupo de linha

- Aula 12: Desafios (Parte 2)
    Fazendo o desafio 14 do material

- Aula 13: Agrupando Colunas com colgroup
    O HTML 5 permite usar a tag colgroup.
         <colgroup>
            <col class="cnome"> *Serve para a primeira coluna*
            <col class="csexo"> *Segunda*
            <col class="cidade"> *terceira*
            <col class="cprof"> *quarta*
        </colgroup>
    Você tambem pode usar o *spean* //Não é colspan
        <colgroup>
            <col class="cnome">
            <col class="cgroup" span="2">
            <col class="cprof">
        </colgroup>

- Aula 14: Tabelas Responsivas
    Coloque a tabela dentro de uma div, assim você pode personalizar o overflow-x da tabela!
        div#container {
            width: 80vw;
            overflow-x: auto;
        }