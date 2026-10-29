# Button Clicker

## Como rodar no VS Code

1. Abra esta pasta no VS Code.
2. Abra o terminal integrado (Terminal > New Terminal).
3. Instale as dependências:
   ```
   npm install
   ```
4. Rode o projeto em modo desenvolvimento:
   ```
   npm run dev
   ```
5. Abra o endereço que aparecer no terminal (geralmente `http://localhost:5173`).

## O que foi corrigido/adicionado nesta versão

- **Bug de formatação corrigido:** 1000 cliques agora mostra "1.00K" corretamente (antes mostrava "1.00M" por um erro de índice na função de formatação).
- **Código reorganizado:** nomes mais claros, constantes nomeadas em vez de números soltos, indentação padronizada, função `fmt()` centralizada em `src/utils/format.js` em vez de duplicada em 4 arquivos.
- **Anel de cursores:** ao redor do botão principal, um anel de ícones de cursor gira — a quantidade de ícones reflete quantos "Cursor" (produtor) você comprou.
- **Autoclique dos Cursores:** N cursores = N pulsos/cliques automáticos por segundo no botão (teto visual de 30 pulsos/s; acima disso o valor de cada pulso aumenta para o total continuar certo).
- **Cursor rebalanceado:** agora produz 1 clique/s e custa 150 (antes 0.1/s e 15).
- **Saves antigos:** cps e custo dos produtores sempre vêm do `gameData.js`; o save guarda só a quantidade comprada.
- **Rebirth linear:** o multiplicador agora é ×2, ×4, ×6, ×8 e ×10 (1º ao 5º rebirth), em vez de ×10 por rebirth. Custos de rebirth reajustados: 8K, 4M, 2B, 800B, 300T.
- **Cursor um rebirth atrás:** a produção do Cursor usa o multiplicador do rebirth anterior (com 0 rebirths segue ×1 como os demais).
- **Cenários pixelados:** cada mapa tem um fundo em pixel art gerado por código (`src/utils/pixelScenes.js`, exibido por `MapScenery.jsx`): Floresta, Floresta Sombria, Vulcão, Mundo de Gelo e Espaço.
- **Upgrades:** reordenados por custo; "Energia de Renascimento" agora dá ×1,5 em todos os cliques (antes não tinha efeito).
- **Produtores rebalanceados:** Cursor 1/s, Vovó 10/s, Fazenda 50/s, Mina 100/s, e custos menores em toda a lista.
- **Fundo dos mapas:** corrigido — o CSS de `.app-bg` sobrescrevia o gradiente do mapa.
- **Números pequenos:** valores abaixo de 10 mostram 1 casa decimal (0.5 deixa de aparecer como "0").
- **Baú removido:** a aba e a funcionalidade do Baú foram retiradas do jogo.

## Estrutura

```
src/
├── App.jsx
├── index.css
├── main.jsx
├── utils/
│   └── format.js
├── data/
│   └── gameData.js
└── components/
    ├── Header.jsx
    ├── Home.jsx
    ├── CursorRing.jsx
    ├── ProducerCard.jsx
    ├── ProducerList.jsx
    └── Sidebar.jsx
```
