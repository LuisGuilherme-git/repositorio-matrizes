Controle de Estoque de Camisetas - Sistema de Gestão Comercial em Python

**Visão Geral e Identificação do Projeto**

O presente projeto consiste no desenvolvimento de um sistema computacional robusto implementado em linguagem Python, concebido com a finalidade primordial de automatizar, controlar e gerenciar o fluxo de estoque de uma loja de vestuário especializada em camisetas. A motivação central por trás desta solução foi a criação de uma ferramenta prática, interativa e funcional capaz de administrar com precisão o inventário de quatro modelos distintos de camisetas, subdivididos em três tamanhos fundamentais: Pequeno (P), Médio (M) e Grande (G). Com essa arquitetura, o sistema assegura o controle rigoroso de todas as entradas e saídas de mercadorias, mantendo a integridade e a organização dos dados logísticos do estabelecimento.

Este trabalho acadêmico foi desenvolvido para a disciplina de Fundamentos da Programação, na Universidade Federal do Norte do Tocantins (UFNT). A concepção, estruturação lógica e implementação do código foram realizadas pela equipe composta pelos integrantes Luís Guilherme, Arthur Resende, Caio Almeida, João Emanuel, Pedro Henrique, Luiz Fernando, Otávio Rodrigues, Luana Nunes e Mayckomar José, aplicando os conceitos fundamentais de manipulação de matrizes, estruturas de repetição, condicionais e modularização por funções.

**Funcionalidades e Operações do Sistema**

O fluxo operacional da aplicação inicia-se imediatamente com uma rotina de cadastro automatizado e validado. Por meio de laços de repetição aninhados, o programa solicita ao operador a quantidade inicial de peças disponíveis para cada combinação de modelo e tamanho. Para resguardar a consistência do banco de dados em memória desde o primeiro segundo de execução, foi implementada uma barreira de validação que intercepta e rejeita qualquer tentativa de inserção de valores negativos, exigindo que o usuário redigite uma quantidade válida antes de prosseguir para o próximo item.

Concluída a etapa de povoamento inicial, o sistema apresenta um menu interativo contínuo que concentra todas as rotinas comerciais da loja. Através dessa interface, o usuário pode realizar consultas pontuais de disponibilidade, registrar vendas com baixa automática no saldo, efetuar reposições de mercadorias recém-chegadas, disparar uma varredura inteligente que alerta sobre produtos com estoque crítico (inferior a três unidades) e gerar um relatório panorâmico exibindo simultaneamente a situação de todo o inventário na tela.

**Estrutura do Código, Funções e Arquitetura de Matriz**

Para garantir a excelência na engenharia de software e evitar redundâncias estruturais, toda a lógica do arquivo sistema_estoque.py foi dividida em funções coesas e especializadas. A função main() atua como o núcleo orquestrador, controlando o cadastro inicial e mantendo o menu principal em execução até que a opção de encerramento seja acionada. As operações cotidianas de consulta, venda e reposição foram centralizadas na função gerenciar_operacao(), que aplica tratamentos de texto com .upper() para aceitar entradas em letras minúsculas, converte os números informados pelo usuário para os índices reais da matriz (iniciados em zero) e executa validações rigorosas que impedem vendas superiores ao saldo disponível ou movimentações com quantidades nulas ou negativas. Complementando o ecossistema, as funções verificar_estoque_baixo() e mostrar_tudo() encarregam-se, respectivamente, de percorrer os dados em busca de itens abaixo do limite de segurança e de formatar a exibição tabular completa para o usuário.

Na camada de armazenamento de dados, o sistema utiliza uma matriz bidimensional. Estruturada como uma lista de listas na memória do Python que funciona exatamente como um armário organizador composto por gavetas e compartimentos. Cada linha horizontal da matriz representa uma gaveta dedicada exclusivamente a um modelo de camiseta, enquanto cada coluna interna atua como uma caixa divisória reservada para armazenar a quantidade exata dos tamanhos P, M e G daquele respectivo modelo, conforme ilustrado na representação estrutural abaixo:

 [ TAMANHO P ]   [ TAMANHO M ]   [ TAMANHO G ]
   (Coluna 0)      (Coluna 1)      (Coluna 2)
 +---------------------------------------------------------------------+
 
Gaveta 0 (Modelo 1)   |   estoque     |   estoque     |   estoque     |
      |    [0][0]     |    [0][1]     |    [0][2]     |
+---------------+---------------+---------------+
Gaveta 1 (Modelo 2)   |   estoque     |   estoque     |   estoque     |
      |    [1][0]     |    [1][1]     |    [1][2]     |
+---------------+---------------+---------------+
Gaveta 2 (Modelo 3)   |   estoque     |   estoque     |   estoque     |
      |    [2][0]     |    [2][1]     |    [2][2]     |
+---------------+---------------+---------------+
Gaveta 3 (Modelo 4)   |   estoque     |   estoque     |   estoque     |
      |    [3][0]     |    [3][1]     |    [3][2]     |
+-----------------------------------------------------------------------+
