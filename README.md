# Nome dos integrantes
João Augusto Zanardo de Lima - 11201920195

Guilherme Klinkerfuss Guimarães Pereira - 11201912414

# Explicação do Projeto

Este projeto foi desenvolvido como parte de uma tarefa acadêmica para demonstrar conceitos avançados de gráficos 3D utilizando OpenGL e a biblioteca ABCg (UFABC Gráfica). O objetivo principal é criar uma aplicação interativa que renderiza modelos 3D, aplicando transformações geométricas e iluminação por meio de shaders.

# Implementações:

## onPaintUI() - Adição de Controles na Interface do Usuário

  O método onPaintUI() é uma extensão do método na classe base abcg::OpenGLWindow e é usado para renderizar a interface do usuário. Adicionamos controles para interagir com as variáveis do programa, como a posição da luz, cor do objeto, intensidade ambiente, intensidade especular e brilho.

## Controles Adicionados:

  Slider para ajustar a posição da luz.
  Color picker para escolher a cor da luz.
  Color picker para escolher a cor do objeto.
  Slider para ajustar a intensidade ambiente.
  Slider para ajustar a intensidade do espectro de luz.
  Slider para ajustar o brilho.
## Como usar:
  Interaja com esses controles para ajustar as variáveis do programa em tempo de execução.

## Detalhes sobre Shaders:
  ### Vertex Shader (depth.vert):
  
  Transforma as coordenadas do objeto no campo de visão.
  Calcula a posição e a normal no espaço do mundo.
  Computa uma cor baseada na profundidade para simular a iluminação.
  
  ### Fragment Shader (depth.frag):
  
  Calcula a iluminação ambiente, difusa e especular.
  Combina as contribuições de iluminação para determinar a cor final do fragmento.
  ## Observações Importantes:
  Certifique-se de que os shaders (depth.vert e depth.frag) estão corretamente escritos e compilados. Erros nos shaders podem causar falhas na execução.
  
  Verifique se as variáveis uniformes nos shaders correspondem às variáveis no código C++. Erros de correspondência podem levar a problemas de renderização.

## Explicação da Window.cpp:
### Função onCreate:

Objetivo: Esta função é chamada quando a janela é criada e é responsável por inicializar muitos aspectos do estado inicial da aplicação.

#### Ações:

Redimensiona o vetor m_fishs para a quantidade especificada por m_fish_quantity.
Obtém o caminho do diretório de assets usando abcg::Application::getAssetsPath() e armazena em m_assetsPath.
Define a cor de fundo usando abcg::glClearColor.
Habilita o teste de profundidade usando abcg::glEnable(GL_DEPTH_TEST).
Compila e linka os shaders do programa OpenGL usando abcg::createOpenGLProgram.
Carrega o modelo 3D especificado por m_object usando m_model.loadObj.
Configura o Vertex Array Object (VAO) para o modelo usando m_model.setupVAO.
Define a matriz de visão (m_viewMatrix) para uma câmera posicionada em (0, 0, 0) olhando para (0, 0, -1) com um vetor para cima (0, 1, 0).
Chama randomizeFish para inicializar aleatoriamente as posições e eixos de rotação das criaturas marinhas.

### Função randomizeFish:

Objetivo: Inicializa aleatoriamente a posição e o eixo de rotação de uma criatura marinha.

### Parâmetros:

Fish &fish: Referência para a estrutura Fish que representa uma criatura marinha.

#### Ações:

Gera coordenadas aleatórias x e y no intervalo (-20, 20) para a posição XY da criatura.
Gera uma coordenada z aleatória no intervalo (-100, 0) para a posição Z da criatura.
Inicializa a posição da criatura com as coordenadas geradas.
Gera um vetor de rotação aleatório esférico (sphericalRand) para o eixo de rotação da criatura.

### Função onUpdate:

Objetivo: Atualiza o estado da aplicação em cada quadro.

#### Ações:

Calcula o delta de tempo (deltaTime) entre quadros usando getDeltaTime.
Atualiza o ângulo de rotação (m_angle) com base no tempo.
Para cada criatura marinha em m_fishs:
Incrementa a coordenada Z da posição da criatura com base no tempo para simular o movimento para a frente.
Se a criatura estiver atrás da câmera (coordenada Z > 0.1), reinicializa sua posição e orientação aleatoriamente e move-a de volta para Z = -100.

### Função onPaint:

Objetivo: Renderiza os objetos na tela.

#### Ações:

Limpa os buffers de cor e profundidade usando abcg::glClear.
Configura o viewport para abranger toda a área da janela usando abcg::glViewport.
Usa o programa OpenGL especificado por m_program usando abcg::glUseProgram.
Obtém as localizações das variáveis de uniforme no programa usando abcg::glGetUniformLocation.
Define variáveis uniformes, como viewMatrix, projMatrix, color, lightPosition, lightColor, objectColor, ambientStrength, specularStrength, shininess.
Renderiza cada criatura marinha:
Calcula a matriz de modelo (modelMatrix) com base na posição, escala, ângulo de rotação e eixo de rotação da criatura.
Define a variável uniforme modelMatrix no programa OpenGL.
Renderiza o modelo 3D da criatura usando m_model.render.
Desativa o programa OpenGL usando abcg::glUseProgram(0).

### Função onPaintUI:

Objetivo: Renderiza a interface do usuário (UI) usando ImGui.

#### Ações:

Chama a função onPaintUI da classe base usando abcg::OpenGLWindow::onPaintUI.
Configura o layout e as propriedades da janela do ImGui.
Renderiza controles da UI, como sliders, botões e caixas de entrada, usando funções do ImGui.
Atualiza parâmetros da aplicação com base nas interações do usuário.



# Para ver o resultado final, acesse o seguinte link no navegador:
https://jozanardo.github.io/Aplicao-grafica-3D-com-animacoes/
