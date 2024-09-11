# Adicionar React

Essa não vai ser a forma comum que vamos utilizar pra adicionar o React, mas neste caso nós vamos conseguir testá-lo sem precisar instalar nada. Vamos precisar de três scripts os dois primeiros são arquivos react o primeiro sendo react puro e o segundo react dom os dois existem porque a biblioteca react também é utilizada para criação de aplicativos mobile no meu caso estou utilizando para um site, então eu vou usar o react dom.

Também tenho um arquivo babel que serve para transformar um código JavaScript novo em um antigo para que funcione em navegadores antigos, mas ele também serve para um transformar um arquivo chamado JSX em arquivo JavaScript porque o JSX não consegue ser lido pelo browser então o babel vai ser o responsável por fazer essa comunicação ocorrer.

#### Os três arquivos abaixo:

```html

<!-- Carrega o React, React Dom e Babel -->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>

    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

    <!-- Don't use this in production: -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

No body, eu preciso de um elemento no qual eu vou criar uma aplicação web com React. Dentro do <script type=””></script> eu preciso indicar que o tipo de script não é JavaScript e sim um script do tipo Babel ele é diferente, pois aqui eu já vou escrever o JSX:

```javascript

<div id="root">
        
</div>

    <script type="text/babel"></script>
```

Agora eu posso começar a criar o meu primeiro componente em React um componente funcional:

```javascript

const App = () => {
    return <div>Teste</div>;
}

```

Aqui já há uma diferença ele vai retornar um HTML porque no JavaScript eu não consigo fazer isso.

Agora eu tenho que montar essa função dentro do root e para isso eu vou precisar de uma função do react que eu utilizo uma única vez pra realmente montar a minha aplicação depois não vou precisar mais dela. Primeiro eu seleciono o root e em seguida eu crio esse objeto root que é o objeto raiz do React e eu só o crio 1 vez na minha aplicação:

```JavaScript

const container = document.getElementById('root');
const root = ReactDOM.createRoot(container);

```
Obs: Essa função ReactDOM veio a partir do momento que eu instalei o react-dom pelo link no head.

Nela, eu tenho uma função chamada createRoot e dentro dela eu passo o meu root. Com o root estabelecido eu posso agora renderizar a minha aplicação 
web:

```JavaScript

root.render(<App />);

```

Dentro dele eu passo de uma forma diferente porque no React um componente funcional que retorna um JSX que se parece com HTML eu vou utilizá-lo como se fosse também uma tag HTML.

Desta forma, quando eu crio componentes funcionais eu posso adicioná-los em qualquer parte do código e quantas vezes for necessário.

```JavaScript

 const Button = () => {
    return <button>Comprar</button>
}

const App = () => {
    return <div>
    <h1>Aplicação web React</h1>
    <Button />
    <Button />
    </div>
}

```

Dentro de Button eu vou criar um estado reativo somente para visualizar que o React está funcionando:

```JavaScript

const [total, setTotal] = React.useState(0);

```

Isso é uma função de React que cria um estado reativo onde eu vou ter primeiro o valor do estado e como incrementar o estado isso é o principal do React que verei mais adiante.

Minha ideia agora é criar um botão que cada vez que eu clico nele a soma acontece e uma das características do React é que adicionando diretamente no botão a função que eu quero que ocorra, por exemplo, no Click:

```JavaScript

const Button = () => {
    const [total, setTotal] = React.useState(0);
    return <button onClick={() => setTotal(total + 1)}>Comprar</button>
}

```

A função setTotal vai atualizar o estado cada vez que eu clicar no botão onde ele vai somar o estado atual mais um.

Na próxima aula verei como ele é realmente adicionado!