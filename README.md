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


# Para ver o resultado final, acesse o seguinte link no navegador:
https://jozanardo.github.io/Aplicao-grafica-3D-com-animacoes/
