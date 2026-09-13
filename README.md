# Ampera

Sistema de monitoramento e gestão de eletropostos — dashboard que reúne, em um único lugar, lucro, gastos com energia, sobrecargas, tarifação, localização dos carregadores e possíveis defeitos, permitindo administrar todos os equipamentos juntos ou individualmente.

## Equipe

| Nome | RM |
|---|---|
| Leonardo Soares Rodrigues | 572986 |
| Rubens Henrique | 572667 |
| Guilherme Cedro | 571050 |
| Gabriel Carvalho | 571381 |
| Felipe Mello | 569237 |
| Matheus Anciães Patelli | 567261 |
| Gabriel Beu Volpato | 563008 |

## Sprint 3 – Prototipagem Funcional e Integração

### Objetivo

Avançar na implementação técnica da solução, demonstrando a integração dos componentes e apresentando um protótipo funcional que evidencia a sinergia entre energia renovável, automação e as tecnologias escolhidas.

### Esquema de integração dos componentes

```
JavaScript (estado dos dados)
        │
        ├── gera HTML dinâmico → injetado no DOM
        │        └── estilizado pelo CSS
        │
        ├── gera SVG dinâmico (gráfico de consumo e mapa da cidade)
        │        └── estilizado/posicionado via CSS
        │
        └── setInterval() → repete o ciclo a cada 7s
                 (recalcula os dados → re-renderiza a tela)
```

- **Login** → simula autenticação (credenciais fixas) e libera o acesso ao dashboard.
- **Cadastro de carregadores** → alimenta o array de dados em memória, que é a fonte única de informação do sistema.
- **Dashboard geral** → soma os dados de todos os carregadores cadastrados (potência, receita, status).
- **Dashboard individual** → filtra e exibe os dados de um único carregador selecionado.
- **Mapa** → posiciona cada carregador cadastrado sobre um mapa de cidade gerado em SVG.
- **Simulação em tempo real** → a cada 7 segundos, a potência de cada carregador varia ±20% em torno do valor cadastrado, e o dashboard, o gráfico e o feed de IA são recalculados e redesenhados automaticamente.

### Justificativa técnica das escolhas

O protótipo foi desenvolvido com **HTML5, CSS3 e JavaScript, por ser suficiente para demonstrar toda a lógica de interface e simulação de dados.

### Resultados e dados funcionais apresentados

- Dashboard com indicadores consolidados: potência total ativa, carregadores ativos, receita, tarifa atual.
- Gráfico de consumo em tempo real, atualizado conforme a variação simulada de potência dos carregadores.
- Cadastro de carregadores, preenchendo dinamicamente o dashboard geral e o mapa.
- Mapa com a localização de cada carregador cadastrado, com indicação visual de status (disponível/offline).
- Dashboard individual por carregador, com os mesmos indicadores filtrados para o equipamento selecionado.
- Feed de decisões automáticas (IA) e painel de tarifação/transações, atualmente simulados.

### Próximos passos (para a versão 100% real)

- Conectar um banco de dados para autenticação real de login e persistência dos carregadores cadastrados.
- Integrar um mapa real da cidade, exibindo a localização verdadeira de cada equipamento.
- Implementar uma IA real, capaz de tomar pequenas decisões automáticas nos carregadores (hoje simuladas).

## Vídeo técnico

Link (não listado): https://www.youtube.com/watch?v=rXYRA4lNW9c
