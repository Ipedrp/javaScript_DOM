- [1. Conteúdo - DOM](#1-conteúdo---dom)
- [2. O que é o DOM?](#2-o-que-é-o-dom)
  - [2.1. Estrutura do DOM](#21-estrutura-do-dom)
- [3. O Objeto console no JavaScript](#3-o-objeto-console-no-javascript)
  - [3.1. Métodos Comuns do console](#31-métodos-comuns-do-console)
- [4. Métodos `alert()`, `prompt()` e `confirm()` no JavaScript](#4-métodos-alert-prompt-e-confirm-no-javascript)
  - [4.1. `alert()`](#41-alert)
  - [4.2. `prompt()`](#42-prompt)
  - [4.3. `confirm()`](#43-confirm)
- [5. Métodos `getElementById` e `getElementsByClassName` no JavaScript](#5-métodos-getelementbyid-e-getelementsbyclassname-no-javascript)
  - [5.1. `getElementById`](#51-getelementbyid)
  - [5.2. `getElementsByClassName`](#52-getelementsbyclassname)
- [6. Métodos `getElementsByName` e `getElementsByTagName` no JavaScript](#6-métodos-getelementsbyname-e-getelementsbytagname-no-javascript)
  - [6.1. `getElementsByName`](#61-getelementsbyname)
  - [6.2. `getElementsByTagName`](#62-getelementsbytagname)
- [7. Métodos `querySelector` e `querySelectorAll` no JavaScript](#7-métodos-queryselector-e-queryselectorall-no-javascript)
  - [7.1. `querySelector`](#71-queryselector)
  - [7.2. `querySelectorAll`](#72-queryselectorall)
- [8. Propriedade `innerHTML` no JavaScript](#8-propriedade-innerhtml-no-javascript)
  - [8.1. Como Funciona](#81-como-funciona)
- [9. Propriedade `classList` no JavaScript](#9-propriedade-classlist-no-javascript)
  - [9.1. Como Funciona](#91-como-funciona)
  - [9.2. Principais Métodos de `classList`](#92-principais-métodos-de-classlist)
- [10. Propriedade `style` no DOM](#10-propriedade-style-no-dom)
  - [10.1. Como Funciona](#101-como-funciona)
- [11. Método `createElement` no DOM](#11-método-createelement-no-dom)
  - [11.1. Como Funciona](#111-como-funciona)
- [12. Métodos `appendChild()` e `removeChild()` no DOM](#12-métodos-appendchild-e-removechild-no-dom)
  - [12.1. Método `appendChild()`](#121-método-appendchild)
  - [12.2. Método `removeChild()`](#122-método-removechild)
- [13. Métodos `getAttribute()`, `setAttribute()` e `removeAttribute()` no DOM](#13-métodos-getattribute-setattribute-e-removeattribute-no-dom)
  - [13.1. Método `getAttribute()`](#131-método-getattribute)
  - [13.2. Método `setAttribute()`](#132-método-setattribute)
  - [13.3. Método `removeAttribute()`](#133-método-removeattribute)
- [14. Propriedades `childNodes` e `parentNode` no DOM](#14-propriedades-childnodes-e-parentnode-no-dom)
  - [14.1. Propriedade `childNodes`](#141-propriedade-childnodes)
  - [14.2. Propriedade `parentNode`](#142-propriedade-parentnode)
- [15. Evento `onclick` no DOM](#15-evento-onclick-no-dom)
  - [15.1. O que é o `onclick`?](#151-o-que-é-o-onclick)
- [16. Eventos `onmouseover` e `onmouseout` no DOM](#16-eventos-onmouseover-e-onmouseout-no-dom)
  - [16.1. O que são os eventos `onmouseover` e `onmouseout`?](#161-o-que-são-os-eventos-onmouseover-e-onmouseout)
- [17. Evento `onLoad` no DOM](#17-evento-onload-no-dom)
  - [17.1. O que é o evento `onLoad`?](#171-o-que-é-o-evento-onload)
- [18. Evento `onSubmit` no DOM](#18-evento-onsubmit-no-dom)
  - [18.1. O que é o evento `onSubmit`?](#181-o-que-é-o-evento-onsubmit)
- [19. Método `addEventListener` no DOM](#19-método-addeventlistener-no-dom)
  - [19.1. O que é o `addEventListener`?](#191-o-que-é-o-addeventlistener)
  - [19.2. Diferença entre `addEventListener` e Eventos Inline](#192-diferença-entre-addeventlistener-e-eventos-inline)
  - [19.3. Uso com Fases de Captura e Propagação](#193-uso-com-fases-de-captura-e-propagação)
  - [19.4. Usos Comuns do `addEventListener`](#194-usos-comuns-do-addeventlistener)

# 1. Conteúdo - DOM
# 2. O que é o DOM?
- O DOM **(Document Object Model)** é uma interface de programação que representa a estrutura de um documento HTML ou XML como uma árvore de objetos. 
- Permite que linguagens de script, como JavaScript: 
  - Acessem
  - Manipulem 
  - Modifiquem dinamicamente o conteúdo, estrutura e estilo de uma página web.
- Quando o navegador carrega uma página web, ele transforma o código HTML em um modelo que pode ser manipulado usando o **DOM**. 
- Cada elemento HTML é representado como um nó ou objeto dentro dessa árvore.

## 2.1. Estrutura do DOM
- A estrutura do **DOM** é hierárquica
- Os elementos podem ser categorizados em diferentes tipos de nós, como:
    - Nó de Documento: Representa o documento em si.
    - Nó de Elemento: Representa elementos HTML, como:
      - `<div>` 
      - `<p>` 
      - `<a>`
    - Nó de Texto: Representa o conteúdo textual dentro de um elemento.
    - Nó de Atributo: Representa os atributos de um elemento HTML.
- Exemplo de Uso:
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>Exemplo de DOM</title>
    </head>
    <body>
        <p id="meuParagrafo">Este é um texto original.</p>
        <button id="alterarConteudo">Alterar Conteúdo e Cor</button>

        <script>
        // Selecionando o parágrafo e o botão
        const paragrafo = document.querySelector("#meuParagrafo");
        const botao = document.querySelector("#alterarConteudo");

        // Adicionando um evento ao botão
        botao.addEventListener("click", function () {
            // Alterando o conteúdo do parágrafo
            paragrafo.innerHTML = "O conteúdo foi alterado com sucesso!";
            // Alterando a cor do texto
            paragrafo.style.color = "blue";
        });
        </script>
    </body>
    </html>
    ```

# 3. O Objeto console no JavaScript
- O objeto console é uma ferramenta poderosa disponível em navegadores e em ambientes como o Node.js. 
- Usado para exibir mensagens, realizar debugging e monitorar o comportamento do código durante sua execução. 
- O console oferece vários métodos úteis para diferentes tipos de saída.
## 3.1. Métodos Comuns do console

- `console.log()`: Para exibir informações gerais durante a execução do código.
  
- `console.error()`: Para reportar erros críticos ou mensagens de falha.
  
- `console.warn()`: Para alertar sobre situações que podem levar a problemas.
  
- `console.info()`: Para mensagens informativas importantes.
  
- `console.table(`: Para visualizar dados de forma mais organizada.
  
- `console.group()` e `console.groupEnd()`: Para organizar e agrupar mensagens de log.
  
- `console.time()` e `console.timeEnd()`: Para medir o desempenho de um código.
  
- `console.clear()`: Para limpar o console em sessões de debugging.
  
- `console.assert()`: Para verificar condições e depurar situações específicas.

- [**Exemplo de Uso - (clique aqui)**](DOM/exemplos/console/index.html)
  
# 4. Métodos `alert()`, `prompt()` e `confirm()` no JavaScript
- Esses três métodos são usados para interagir diretamente com o usuário por meio de caixas de diálogo no navegador. 
- Eles são simples, mas úteis para exibir mensagens, coletar dados ou solicitar confirmações.
  
## 4.1. `alert()`
  - Exibe uma caixa de diálogo com uma mensagem e um botão "OK". 
  - Ele é geralmente usado para informar algo ao usuário.

## 4.2. `prompt()`
  - Exibe uma caixa de diálogo com uma mensagem, um campo de entrada de texto e os botões "OK" e "Cancelar". 
  - Ele permite que o usuário insira informações.

## 4.3. `confirm()`
  - Exibe uma caixa de diálogo com uma mensagem e dois botões: "OK" e "Cancelar". 
  - Ele retorna um valor booleano baseado na escolha do usuário.
  
- [**Exemplo de Uso - (clique aqui)**](DOM/exemplos/alert_confirm_prompt/index.html)


# 5. Métodos `getElementById` e `getElementsByClassName` no JavaScript
- Os métodos `getElementById` e `getElementsByClassName` são usados para selecionar elementos HTML com base em seus IDs ou classes. 
- Eles fazem parte da API do DOM e são amplamente utilizados para manipular elementos da página.
  
## 5.1. `getElementById`
- É usado para selecionar um elemento HTML único com base no valor do seu atributo id.

- Exemplo de Uso:

    ```js
    const elemento = document.getElementById("id");
    ```
- Parâmetro: O valor do atributo id do elemento que você deseja selecionar.
- Retorno: Um único elemento HTML ou null se nenhum elemento for encontrado.
  
## 5.2. `getElementsByClassName`
- É usado para selecionar todos os elementos que possuem uma determinada classe. 
- Ele retorna uma HTMLCollection (uma coleção ao vivo de elementos).

- Exemplo de Uso:
    ```js
    const elementos = document.getElementsByClassName("classe");
    ```
- Parâmetro: O valor do atributo class dos elementos que você deseja selecionar.
- Retorno: Uma coleção de elementos (HTMLCollection) ou uma coleção vazia se nenhum elemento for encontrado.
  
- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/getElementById_getElementByClassName/index.html)


# 6. Métodos `getElementsByName` e `getElementsByTagName` no JavaScript

- Os métodos `getElementsByName` e `getElementsByTagName` são usados para selecionar elementos HTML com base no atributo `name` ou no nome da tag. 
- Ambos retornam coleções de elementos que podem ser manipuladas via DOM.

## 6.1. `getElementsByName`
- Retorna uma coleção de elementos (NodeList) que possuem o atributo `name` com o valor especificado.

- Exemplo de Uso:

    ```js
    const elementos = document.getElementsByName("nome");
    ```
- Parâmetro: O valor do atributo name que você deseja selecionar.
- Retorno: Uma NodeList contendo os elementos que possuem o atributo `name` com o valor especificado.

  
## 6.2. `getElementsByTagName`
- Retorna uma coleção de elementos (HTMLCollection) que possuem o nome da tag especificado.

- Exemplo de Uso:

    ```js
    const elementos = document.getElementsByTagName("div");
    ```
- Parâmetro: O nome da tag HTML que você deseja selecionar (ex.: `div`, `p`, `input`).
- Retorno: Uma HTMLCollection contendo todos os elementos com o nome da tag especificado.

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/getElementByName_getElementsByTagName/index.html)


# 7. Métodos `querySelector` e `querySelectorAll` no JavaScript
- Os métodos `querySelector` e `querySelectorAll` são usados para selecionar elementos do DOM usando seletores CSS. 
- Eles são extremamente flexíveis e permitem selecionar elementos com base em `IDs`, `classes`, `tags`, `pseudo-classes` e combinações de seletores.

##  7.1. `querySelector`
- Retorna o primeiro elemento que corresponde ao seletor CSS fornecido. Se nenhum elemento corresponder, ele retorna null.

- Exemplo de Uso:

    ```js
    const elemento = document.querySelector("#titulo");
    ```
- Parâmetro: Um seletor CSS (ex.: `#id`, `.classe`, `tag`, etc.)
- Retorno: O primeiro elemento correspondente ao seletor ou null.

## 7.2. `querySelectorAll`
- Retorna todos os elementos que correspondem ao seletor CSS fornecido. Ele retorna uma NodeList, que pode ser iterada com `forEach`.

- Exemplo de Uso:

    ```js
    const elementos = document.querySelectorAll("#titulo");
    ```
- Parâmetro: Um seletor CSS (ex.: `#id`, `.classe`, `tag`, etc.)
- Retorno: Uma NodeList contendo todos os elementos correspondentes.


- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/querySelector_querySelectorAll/index.html)

# 8. Propriedade `innerHTML` no JavaScript
- É usada para obter ou definir o conteúdo HTML de um elemento. 
- É uma ferramenta poderosa e prática para manipular o DOM, permitindo inserir ou substituir conteúdo diretamente dentro de um elemento HTML.
  
## 8.1. Como Funciona
- Ler o conteúdo HTML de um elemento:
  - Usando innerHTML, você pode acessar o conteúdo interno de um elemento HTML, incluindo texto e tags.

- Alterar o conteúdo HTML de um elemento:
  - Também é possível redefinir o conteúdo de um elemento, substituindo tudo o que está dentro dele.

- [**Exemplo de Uso - (clique aqui)**](DOM/exemplos/innerHTML/index.html)

# 9. Propriedade `classList` no JavaScript
- É uma interface que fornece métodos convenientes para manipular as classes CSS de um elemento HTML. 
- Com ela, você pode adicionar, remover, alternar ou verificar a existência de classes em um elemento sem precisar lidar diretamente com a string da propriedade `className`.

## 9.1. Como Funciona
- Retorna um DOMTokenList, que é uma coleção de classes aplicadas a um elemento. 
- Você pode usar os métodos dessa interface para modificar as classes.

## 9.2. Principais Métodos de `classList`

- `classList.add(className)`
  - Adiciona uma ou mais classes ao elemento.

- `classList.remove(className)`
    - Remove uma ou mais classes do elemento.

- `classList.toggle(className)`
    - Adiciona a classe ao elemento se ela não existir; remove a classe se ela já existir.

- `classList.contains(className)`
    - Verifica se o elemento possui a classe especificada. Retorna `true` ou `false`.

- `classList.replace(oldClass, newClass)`
    - Substitui uma classe existente por outra.

- Exemplo de Uso:
    ```js
    elemento.classList.add("classe1", "classe2");

    elemento.classList.remove("classe");

    elemento.classList.toggle("classe");

    elemento.classList.contains("classe"); 

    elemento.classList.replace("antiga", "nova");
    ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/classList/index.html)

# 10. Propriedade `style` no DOM
- É usada para manipular os estilos CSS de um elemento diretamente por meio de JavaScript. 
- Permite acessar e modificar os estilos inline de um elemento HTML.

## 10.1. Como Funciona

- A propriedade `style` é um objeto que contém várias propriedades correspondentes aos estilos CSS. 
- Essas propriedades podem ser lidas ou modificadas diretamente, e os nomes das propriedades CSS são convertidos de **kebab-case** para **camelCase**.

- Exemplo de Conversão de Propriedades CSS
  - CSS: `background-color` → JavaScript: `backgroundColor`
  - CSS: `font-size` → JavaScript: `fontSize`
  - CSS: `margin-top` → JavaScript: `marginTop`
  
- Exemplo de Uso:

    ```js
    const titulo = document.getElementById("titulo");

    // Alterando estilos com a propriedade style
    titulo.style.color = "blue";       
    titulo.style.fontSize = "24px";   
    titulo.style.textAlign = "center"; 
    ```
# 11. Método `createElement` no DOM

- É utilizado para criar elementos HTML de forma dinâmica com JavaScript.  
- Permite criar elementos que podem ser personalizados, configurados e inseridos no DOM.

## 11.1. Como Funciona

- A função `createElement` cria um novo elemento HTML especificado pela tag fornecida.  
- Este elemento é inicialmente desconectado do DOM, podendo ser configurado antes de ser adicionado.  

- Exemplo de Uso:
  ```js
  const novoElemento = document.createElement("div");
  ```
- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/createElement/index.html)

# 12. Métodos `appendChild()` e `removeChild()` no DOM

- São amplamente usados para manipular a árvore DOM. Eles permitem adicionar e remover elementos do DOM de forma dinâmica.

## 12.1. Método `appendChild()`

- É utilizado para adicionar um elemento filho a um elemento pai no DOM.  
- Adiciona o novo elemento como o **último filho** do elemento pai.

- Sintaxe:
  ```js
    parentNode.appendChild(childNode);
  ```

  - parentNode: O elemento pai onde o elemento será inserido.
  - childNode: O elemento a ser adicionado como filho.

- Exemplo de Uso:
  ```js
  // Criar um novo elemento <p>
  const novoParagrafo = document.createElement('p');
  novoParagrafo.textContent = 'Este é um parágrafo adicionado dinamicamente.';

  // Selecionar o elemento pai
  const container = document.getElementById('container');

  // Adicionar o parágrafo ao container
  container.appendChild(novoParagrafo);
  ```
## 12.2. Método `removeChild()`

- É usado para remover um elemento filho de seu elemento pai no DOM.

- Requer uma referência ao elemento filho que será removido.

- Sintaxe:
  ```js
  parentNode.removeChild(childNode);
  ```

  - parentNode: O elemento pai que contém o elemento a ser removido.
  - childNode:  O elemento filho que será removido.

- Exemplo de Uso:
  ```js
  // Selecionar o elemento pai
  const lista = document.getElementById('minhaLista');

  // Selecionar o elemento filho a ser removido
  const itemParaRemover = document.getElementById('item1');

  // Remover o elemento filho
  lista.removeChild(itemParaRemover);

  ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/appendChild_removeChild/index.html)

# 13. Métodos `getAttribute()`, `setAttribute()` e `removeAttribute()` no DOM

- São usados para manipular atributos de elementos HTML no DOM. Esses métodos permitem acessar, definir e remover atributos de maneira eficiente.

## 13.1. Método `getAttribute()`

- É utilizado para obter o valor de um atributo específico de um elemento HTML.  
- Retorna `null` se o atributo não estiver definido.

- Sintaxe:
  ```js
  element.getAttribute(attributeName);
  ```
  - attributeName: O nome do atributo que você deseja acessar.

- Exemplo de Uso:
  ```js
  const link = document.getElementById('meuLink');

  // Obter o valor do atributo href
  const href = link.getAttribute('href');
  console.log(href); // Exemplo: "https://www.exemplo.com"
  ```
## 13.2. Método `setAttribute()`

- É usado para adicionar ou atualizar o valor de um atributo em um elemento HTML.
- Retorna `null` se o atributo não estiver definido.

- Sintaxe:
  ```js
  element.setAttribute(attributeName, value);
  ```
  - attributeName: O nome do atributo que será adicionado ou atualizado.
  - value: O valor que será atribuído ao atributo.

- Exemplo de Uso:
  ```js
  const botao = document.getElementById('meuBotao');

  // Definir o atributo disabled no botão
  botao.setAttribute('disabled', 'true');

  // Atualizar o atributo title
  botao.setAttribute('title', 'Botão desativado');

  ```
## 13.3. Método `removeAttribute()`

- É utilizado para remover um atributo de um elemento HTML.

- Sintaxe:
  ```js
  element.removeAttribute(attributeName);
  ```
  - attributeName: O nome do atributo que será removido.

- Exemplo de Uso:
  ```js
  const input = document.getElementById('meuInput');

  // Remover o atributo readonly
  input.removeAttribute('readonly');
  ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/getAttribute_setAttribute_removeAttribute/index.html)

# 14. Propriedades `childNodes` e `parentNode` no DOM

- Sãofundamentais para navegar e manipular a estrutura da árvore DOM. 
- Permitem acessar elementos relacionados a um nó específico.

## 14.1. Propriedade `childNodes`

- Retorna uma **NodeList** contendo todos os nós filhos de um elemento, incluindo:  
  - Elementos (tags HTML)  
  - Nós de texto (espaços em branco, quebras de linha, etc.)  
  - Comentários

- Sintaxe:
  ```js
  element.childNodes;
  ```` 
- Exemplo de Uso:
  ```js
  const lista = document.getElementById('minhaLista');

  // Obter os nós filhos da lista
  const filhos = lista.childNodes;

  // Exibir os nós filhos no console
  filhos.forEach((nodo) => console.log(nodo));

  ```
  - Acessando Nós Específicos: 
   
    ```js
    const primeiroFilho = lista.childNodes[0]; // Primeiro nó filho
    console.log(primeiroFilho);
    ```
  - Importante: Para obter somente os elementos filhos (ignorando nós de texto e comentários), use `children`:
   
    ```js
    const elementosFilhos = lista.children;
    console.log(elementosFilhos);
    ```

## 14.2. Propriedade `parentNode`
- Retorna o nó pai do elemento atualPermite navegar na árvore DOM para acessar o elemento pai de qualquer nó.

- Sintaxe:
  ```js
  element.parentNode;
  ```` 
- Exemplo de Uso:
  ```js
  const item = document.getElementById('item1');

  // Obter o nó pai do item
  const pai = item.parentNode;

  console.log(pai); // Exibe o elemento pai no console
  ```
- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/childNodes_parentNode/index.html)

# 15. Evento `onclick` no DOM

- É um dos eventos mais comuns no JavaScript, utilizado para capturar e responder a cliques do usuário em elementos HTML. 
- Permite executar uma função sempre que o usuário clicar em um determinado elemento.

## 15.1. O que é o `onclick`?

- Acionado quando o usuário clica com o mouse sobre um elemento da página, como um botão, uma imagem ou um link.
- Pode ser atribuído diretamente no HTML ou através de JavaScript.
  
- Exemplo de Uso:
  ```js
  const botao = document.getElementById('meuBotao');

  botao.onclick = function() {
  alert('Você clicou no botão!');
  };
  ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/onClick/index.html)
  
# 16. Eventos `onmouseover` e `onmouseout` no DOM

Os eventos `onmouseover` e `onmouseout` são usados para detectar quando o mouse entra e sai de um elemento na página. Esses eventos são comumente usados para criar efeitos interativos e de destaque.

---

## 16.1. O que são os eventos `onmouseover` e `onmouseout`?

- **`onmouseover`:** É acionado quando o ponteiro do mouse entra dentro de um elemento.
- **`onmouseout`:** É acionado quando o ponteiro do mouse sai de um elemento.

- Esses eventos são muito úteis para criar efeitos de destaque, como:
  - Alterar a cor de um botão ao passar o mouse sobre ele
  - Ocultar informações ao mover o mouse para fora de um elemento.


- Sintaxe 

  - Atribuindo diretamente no HTML:
      ```html
      <elemento onmouseover="codigoJavaScript" onmouseout="codigoJavaScript">
          Texto ou Conteúdo
      </elemento>
      ```

  - Atribuindo no JavaScript:
      ```js
      elemento.onmouseover = function() {
          // Código a ser executado quando o mouse entrar no elemento
      };
      
      elemento.onmouseout = function() {
          // Código a ser executado quando o mouse sair do elemento
      };
      ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/onMouseOver_onMouseOut/index.html)
  
# 17. Evento `onLoad` no DOM

- É utilizado para indicar que um recurso (como uma página HTML, uma imagem ou um arquivo de áudio) foi completamente carregado. - - Muito útil para realizar ações assim que os elementos de uma página estiverem prontos para serem manipulados.

## 17.1. O que é o evento `onLoad`?

- É disparado quando o navegador termina de carregar completamente um recurso. 
- Pode ser aplicado a diferentes tipos de recursos, como a própria página HTML, imagens, scripts, folhas de estilo, entre outros.
- Ele é amplamente utilizado para executar funções JavaScript assim que todos os elementos de uma página estiverem disponíveis, garantindo que o código seja executado somente depois que todos os recursos forem carregados.

- Sintaxe

  - Atribuindo diretamente no HTML:
      ```html
      <elemento onload="codigoJavaScript">
          Conteúdo
      </elemento>
      ```

  - Atribuindo no JavaScript:
      ```js
      elemento.onload = function() {
          // Código a ser executado após o carregamento completo do recurso
      };
      ```

- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/onLoad/index.html)

# 18. Evento `onSubmit` no DOM

- É usado para capturar e manipular o envio de formulários em uma página web. 
- É acionado quando o formulário é enviado, permitindo que você execute validações, impeça o envio padrão ou tome outras ações antes de processar os dados do formulário.

## 18.1. O que é o evento `onSubmit`?

- É disparado sempre que o botão de envio de um formulário é clicado ou quando o usuário pressiona "Enter" dentro de um campo de texto em um formulário.
- Ele é comumente utilizado para validar os dados do formulário antes de enviá-los ao servidor ou para impedir o envio caso os dados estejam incorretos.

- Sintaxe

  - Atribuindo diretamente no HTML:
      ```html
      <form onsubmit="codigoJavaScript">
          <!-- Campos do formulário -->
      </form>
      ```

  - Atribuindo no JavaScript:
      ```js
      const formulario = document.getElementById('meuFormulario');
      formulario.onsubmit = function(event) {
          // Código a ser executado quando o formulário for enviado
      };
      ```
- [**Exemplo de Uso Completo - (clique aqui)**](DOM/exemplos/onSubmit/index.html)

# 19. Método `addEventListener` no DOM

- É utilizado para adicionar ouvintes de eventos a elementos no DOM. 
- Permite associar uma função a um evento específico, como: 
  - cliques
  - carregamento de página
  - digitação
  - etc...
- Oferece maior flexibilidade em relação à manipulação de eventos.

## 19.1. O que é o `addEventListener`?

- Permite que você registre funções que serão executadas quando um evento for disparado.
- Diferente de atribuir eventos diretamente (como `onclick`), o `addEventListener` permite adicionar múltiplos ouvintes ao mesmo elemento e evento, sem sobrescrever os existentes.

- Sintaxe 

  ```js
  elemento.addEventListener(tipoEvento, funcao, usoCaptura);
  ```

- Parâmetros:
  
  - **tipoEvento** (obrigatório): O tipo de evento a ser escutado, como:
    - `"click"`
    - `"mouseover"`
    - `"submit"`, 
    - etc...
  - **funcao** (obrigatório): A função a ser executada quando o evento for disparado.
  - **usoCaptura** (opcional): Um booleano que indica se o evento será capturado na fase de captura (`true`) ou na fase de propagação (`false`, padrão).

- Exemplo de Uso:

  - Adicionando um Evento de Clique

    - **HTML:**
        ```html
        <button id="botao">Clique aqui</button>
        ```

    - **JavaScript:**
        ```js
        const botao = document.getElementById('botao');

        botao.addEventListener('click', function() {
            alert('Botão clicado!');
        });
        ```

    - **Comportamento:** Ao clicar no botão, uma mensagem de alerta será exibida.

  - Removendo um Ouvinte de Evento

    - Para remover um evento adicionado com `addEventListener`, é necessário que a função usada seja declarada separadamente.

    - **HTML:**
        ```html
        <button id="botao">Clique aqui</button>
        <button id="remover">Remover Evento</button>
        ```
    - **JavaScript:**

        ```js
        const botao = document.getElementById('botao');
        const remover = document.getElementById('remover');

        function exibirAlerta() {
            alert('Botão clicado!');
        }

        botao.addEventListener('click', exibirAlerta);

        remover.addEventListener('click', function() {
            botao.removeEventListener('click', exibirAlerta);
            alert('Evento removido!');
        });
        ```
    - **Comportamento:** Ao clicar no botão "Remover Evento", o evento de clique do primeiro botão será desativado.

  - Adicionando Múltiplos Eventos

    - Com o `addEventListener`, é possível adicionar múltiplos eventos ao mesmo elemento.

    - **HTML:**
        ```html
        <button id="botao">Passe o mouse ou clique</button>
        ```

    - **JavaScript:**
        ```js
        const botao = document.getElementById('botao');

        botao.addEventListener('click', function() {
            console.log('Botão clicado!');
        });

        botao.addEventListener('mouseover', function() {
            console.log('Mouse passou por cima do botão!');
        });
        ```
    - **Comportamento:** Tanto o clique quanto o movimento do mouse sobre o botão disparam eventos diferentes.
  
  - `addEventListener` com Parâmetros em Funções

    - Se for necessário passar parâmetros para a função do evento, utilize uma função anônima para encapsular a chamada.

      - **HTML:**
          ```html
          <button id="botao">Clique aqui</button>
          ```
      - **JavaScript:**
          ```js
          const botao = document.getElementById('botao');

          botao.addEventListener('click', function() {
              exibirMensagem('Olá, mundo!');
          });

          function exibirMensagem(mensagem) {
              alert(mensagem);
          }
          ```
      - **Comportamento:** O clique no botão exibirá a mensagem "Olá, mundo!".

## 19.2. Diferença entre `addEventListener` e Eventos Inline

- **Eventos Inline (`onclick`)**: Define um único ouvinte de evento diretamente no elemento HTML. Substitui qualquer ouvinte existente.
- **`addEventListener`**: Permite adicionar múltiplos ouvintes ao mesmo elemento e evento. Não sobrescreve ouvintes existentes.

## 19.3. Uso com Fases de Captura e Propagação

O terceiro parâmetro de `addEventListener` controla se o evento será capturado na **fase de captura** (`true`) ou na **fase de propagação** (`false`, padrão).

- **HTML:**
    ```html
    <div id="pai" style="padding: 20px; background-color: lightblue;">
        <button id="filho">Clique aqui</button>
    </div>
    ```
- **JavaScript:**
    ```js
    const pai = document.getElementById('pai');
    const filho = document.getElementById('filho');

    pai.addEventListener('click', function() {
        console.log('Evento no pai!');
    }, true); // Fase de captura

    filho.addEventListener('click', function() {
        console.log('Evento no filho!');
    });
    ```

- **Comportamento:** Quando o botão for clicado, o evento no pai será registrado primeiro devido à fase de captura.

## 19.4. Usos Comuns do `addEventListener`

- **Clique em botões (`click`)**
- **Movimento do mouse (`mouseover`, `mouseout`)**
- **Eventos de teclado (`keydown`, `keyup`)**
- **Envio de formulários (`submit`)**
- **Carregamento de página (`DOMContentLoaded`)**

