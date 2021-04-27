# React Lifecycle

Podemos pensar em React Lifecycle como, assim como o nome ja diz, um ciclo de vida mesmo. É uma série de eventos que acontece com o componente desde o momento em que ele é criado até ele morrer, digamos assim.

Os métodos mais comuns de ciclo de vida no React são:

## render();

- O `render` é requirido em todas os componentes do React;
- Ele retorna JSX que foi montada no componente;
- Pode retornar `null` se não houver nada para renderizar;
- Não pode conter efeitos separados, ou seja, deve retornar o mesmo output com o input que lhe foi passado;
- Não é possível modificar o estado do componente em `render()`.

## componentDidMount()

- É chamado assim que o componente está montado;
- Bom lugar para chamar APIs;
- Diferente do `render()`, ele permite o uso do `setState()`. Chamar o `setState()` aqui irá fazer um update do estado e causar outra renderização **antes** do browser fazer update na sua interface.

## componentDidUpdate()

- É invocado assim que um update acontece;
- A causa mais comum de uso para este método é de update no DOM em resposta a mudanças em props ou states;
- Você pode chamar `setState()` neste ciclo de vida mas é necessário encapsulá-lo em uma condição para que você não termine com um loop infinito.

## componentWillUnmount()

- Chamado antes do componente ser desmontado e finalizado;
- Melhor lugar para fazer as limpezas no código;
- Não é possível modificar o estado do componente neste ciclo de vida.
