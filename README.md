# Roleta — Rancho da Beato

Jogo social local para 2 a 20 pessoas, com roleta SVG dinâmica e copos simbólicos. A participação é voluntária e não exige consumo de álcool.

## Executar

Sirva a pasta do projeto com um servidor HTTP estático, por exemplo `python3 -m http.server 8000` e acesse localhost:8000. Não há dependências de instalação ou backend.

## Regras

A roleta escolhe o iniciador; a roleta sorteia outra pessoa. O destinatário pode aceitar, recusar ou passar; ao passar, a roleta sorteia o próximo destinatário, dobrando o multiplicador de 1× para 2× e 4×. Em 4× não há passagem. A pessoa atual e o destinatário imediatamente anterior não são elegíveis para a próxima transferência. Após a resolução começa o intervalo configurável; a próxima rodada é manual.

A sessão e configurações são guardadas em LocalStorage neste navegador. O tempo é calculado com timestamps e pode ser pausado. Limpar os dados do navegador apaga a sessão.

## Implementação

O `index.html` na raiz é a entrada do jogo. HTML, CSS e JavaScript ES modules sem build; SVG da roleta, fichas, cartas, copos e relógio são gerados no código. Sorteios usam Web Crypto com rejeição de viés. A página respeita movimento reduzido e oferece seleção por lista. Publicação possível em qualquer hospedagem estática.
