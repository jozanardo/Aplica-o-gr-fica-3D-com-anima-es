# Nome dos integrantes
João Augusto Zanardo de Lima - 11201920195

Guilherme Klinkerfuss Guimarães Pereira - 11201912414

# Explicação do Projeto

Este projeto foi desenvolvido como parte de uma tarefa acadêmica para demonstrar conceitos avançados de gráficos 3D utilizando OpenGL e a biblioteca ABCg (UFABC Gráfica). O objetivo principal é criar uma aplicação interativa que renderiza modelos 3D, aplicando transformações geométricas e iluminação por meio de shaders.

# Funcionalidades Implementadas
## 1. Modelos 3D e Transformações Geométricas
Implementação de primitivas OpenGL e transformações geométricas.
Utilização da classe Model para carregar modelos OBJ, configurando VAOs e VBOs.
## 2. Animação e Movimento
Animação simulando a movimentação de peixes no mar.
Utilização de instâncias da estrutura Fish com posições e eixos de rotação aleatórios.
## 3. Controle de Projeção
Alternância entre projeção perspectiva e ortográfica.
Controle do campo de visão (FOV) na projeção perspectiva e ajuste da escala na projeção ortográfica.
## 4. Seleção de Modelos
Escolha dinâmica entre diferentes modelos 3D (peixe bebê, peixe-balão, tubarão).
Recarregamento da cena e reinício da animação ao selecionar um novo modelo.
## 5. Iluminação
Implementação de shaders para iluminação ambiente, difusa e especular.
Controle dinâmico da posição da luz, cor da luz, cor do objeto, força ambiente, força especular e intensidade de brilho pelo usuário.
## Detalhes dos Shaders
Transformação de coordenadas de vértices para o espaço de olho.
Cálculo de vetores normais e aplicação de iluminação ambiental.
Definição da posição final do vértice após aplicar as matrizes de modelo, visão e projeção.
## Iluminação difusa, especular e ambiental.
Recebimento de informações do Vertex Shader, como posição do fragmento, vetor normal e cor.
Aplicação das fórmulas de iluminação e envio do resultado final para a saída.
## Interface Gráfica de Controle
Interface gráfica interativa usando ImGui.
Controle dinâmico de variáveis importantes, como posição da luz, cor da luz, cor do objeto, intensidades de iluminação, escala e modelo selecionado.
## Reload Shaders
Implementação de um botão "Reload Shaders" para recarregar os shaders em tempo de execução, facilitando o desenvolvimento e a depuração.

# Para ver o resultado final abre no navegador:
https://jozanardo.github.io/Aplicao-grafica-3D-com-animacoes/
