# 🧮 Calculadora

Calculadora web simples, responsiva e sem dependências, feita com HTML, CSS e JavaScript puro.

## ✨ Funcionalidades

- Operações básicas: soma (`+`), subtração (`-`), multiplicação (`*`) e divisão (`÷`)
- Números decimais
- `AC` limpa tudo e `DEL` apaga o último dígito
- Encadeamento de operações (ex.: `2 + 3 *` calcula `2 + 3` antes de continuar)
- Display com a operação anterior e o número atual, com separador de milhar
- Layout responsivo para celulares, tablets e desktop (inclusive em modo paisagem)

## 🛠️ Tecnologias

- **HTML5**: estrutura semântica com atributos `data-*` para ligar os botões ao JS
- **CSS3**: CSS Grid, variáveis CSS, `clamp()` e media queries
- **JavaScript (ES6+)**: classe `Calculator` com a lógica separada da interface
- **Google Fonts**: Roboto

## 🚀 Como executar

Não é necessário instalar nada.

1. Clone o repositório:
   ```bash
   git clone <url-do-repositorio>
   cd calculator-project
   ```
2. Abra o arquivo `index.html` no navegador (duplo clique ou "Abrir com").

Opcionalmente, use um servidor local, como a extensão **Live Server** do VS Code.

## 📁 Estrutura do projeto

```
calculator-project/
├── index.html   # Estrutura da calculadora
├── style.css    # Estilos e responsividade
├── script.js    # Lógica da calculadora
└── README.md
```

## 📱 Responsividade

O tamanho dos botões é controlado pela variável CSS `--cell-size`, que usa `clamp()` para se ajustar à largura da tela (entre 60px e 100px). Ajustes adicionais por media query:

| Cenário | Comportamento |
| --- | --- |
| Telas até 360px | Calculadora ocupa quase toda a largura (`24vw` por botão) |
| Celular em paisagem (altura ≤ 560px) | Botões menores, baseados na altura da tela |
| Telas grandes (≥ 1200×800) | Botões de 110px |
| Demais telas | Botões fluidos de 60px a 100px |

As fontes do display e dos botões também escalam com `clamp()`.

## 🧠 Como funciona

A classe `Calculator` em [script.js](script.js) guarda três estados: `previousOperand`, `currentOperand` e `operation`. Os métodos principais são:

| Método | Função |
| --- | --- |
| `appendNumber(n)` | Adiciona um dígito ou ponto (ignora pontos duplicados) |
| `chooseOperation(op)` | Define a operação e move o número atual para o anterior |
| `calculate()` | Executa a operação e coloca o resultado no display |
| `delete()` | Remove o último caractere |
| `clear()` | Reinicia o estado |
| `updateDisplay()` | Atualiza o display formatado |

## 🔮 Melhorias futuras

- Suporte ao teclado
- Tratamento de divisão por zero
- Botão de porcentagem e inversão de sinal
- Histórico de cálculos
- Tema claro/escuro

## 📄 Licença

Projeto de uso livre para fins de estudo.
