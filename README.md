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

### Como usar o protótipo

1. Acesse o link do protótipo: https://felipemello987.github.io/Sprint-3-prototipo-Ampera/
2. Na tela de login, use as credenciais:
   - **Email:** `admin123@gmail.com`
   - **Senha:** `123123`
3. Após entrar, use o menu lateral para navegar entre **Dashboard** e **Mapa**.
4. No Dashboard, clique em **"+ Cadastrar carregador"** e preencha nome, potência (kW), faturamento (R$) e status. Isso preenche automaticamente os cards, o gráfico, a lista de status e o mapa.
5. Clique em qualquer carregador da lista para abrir o **dashboard individual** daquele equipamento (com o gráfico de consumo isolado).
6. Na aba **Mapa**, veja a localização de cada carregador cadastrado — verde para disponível/carregando, vermelho para offline.
7. A cada 7 segundos, a potência dos carregadores varia automaticamente (±20% do valor cadastrado), simulando o funcionamento em tempo real, junto com o feed de decisões da IA e as transações simuladas.

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

### Contribuição das tecnologias para sustentabilidade, automação e eficiência energética

- **Dashboard consolidado (HTML/CSS/JS):** ao reunir consumo, receita e status de todos os carregadores em tempo real, permite que o proprietário identifique rapidamente equipamentos ociosos ou sobrecarregados, favorecendo um uso mais eficiente da energia disponível.
- **Simulação em tempo real (JavaScript):** a variação automática de potência a cada 7 segundos simula o comportamento real do consumo elétrico, servindo de base para futuras decisões automatizadas de distribuição de carga (balanceamento entre carregadores).
- **Feed de decisões automáticas (IA simulada):** representa a camada de automação inteligente prevista para a versão final, priorizando veículos, redistribuindo carga entre equipamentos e evitando picos de demanda — reduzindo desperdício de energia.
- **Painel de tarifação:** ao expor tarifas de pico, normal e off-peak, incentiva o uso consciente da energia em horários mais baratos e menos sobrecarregados, contribuindo para a eficiência da rede como um todo.

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
