## Integrantes do Grupo

- Enzo Rocha Damato - RA: 10175268
- Enrique Granado Novaes - RA: 10276914
- Gabriel Santos de Oliveira Arruda - RA: 10388025
- Paulo Henrique Sousa Camargo - RA: 10389453

# APIs-gr-ficas# Pesquisa sobre API Gráfica: OpenGL

## Descrição da API OpenGL

A OpenGL (Open Graphics Library) é uma API gráfica que fornece uma maneira padronizada de acessar recursos gráficos de hardware. Ela é projetada para ser usada em aplicações que exigem gráficos 2D e 3D, como jogos, simulações científicas e aplicações de visualização de dados. A OpenGL é uma API de baixo nível que oferece controle direto sobre o hardware gráfico, permitindo aos desenvolvedores otimizar o desempenho e a eficiência dos gráficos.

## Documentação da Pipeline pela OpenGL

A documentação da pipeline gráfica pela OpenGL é detalhada e abrange desde a especificação do OpenGL até a implementação de shaders e técnicas de renderização. A pipeline gráfica da OpenGL é composta por várias etapas, incluindo a especificação de vértices e atributos de vértices, transformação de vértices, culling, rasterização, sombreamento e composição. A documentação fornece informações detalhadas sobre como cada etapa funciona e como os desenvolvedores podem interagir com a pipeline para criar gráficos personalizados.

## Linguagens de Shading Suportadas pela OpenGL

A OpenGL suporta várias linguagens de shading, incluindo:

- **GLSL (OpenGL Shading Language):** Uma linguagem de shading específica para gráficos 3D. Ela é usada para escrever shaders de vértices e fragmentos que são executados no GPU.
- **Cg (C for Graphics):** Uma linguagem de shading que também é usada para escrever shaders de vértices e fragmentos. Ela é suportada pela NVIDIA e pela AMD.
- **HLSL (High-Level Shading Language):** Uma linguagem de shading da Microsoft usada principalmente em aplicações DirectX.

## Exemplo de Código OpenGL

```cpp
#include <GL/glew.h>
#include <GLFW/glfw3.h>

int main() {
    // Inicializa a GLFW
    if (!glfwInit()) {
        return -1;
    }

    // Cria uma janela
    GLFWwindow* window = glfwCreateWindow(640, 480, "Hello Triangle", NULL, NULL);
    if (!window) {
        glfwTerminate();
        return -1;
    }

    // Faz o contexto da janela atual
    glfwMakeContextCurrent(window);

    // Carrega as funções da OpenGL usando GLEW
    glewInit();

    // Habilita o VSync para sincronização vertical
    glfwSwapInterval(1);

    // Loop principal
    while (!glfwWindowShouldClose(window)) {
        // Processa eventos da janela
        glfwPollEvents();

        // Limpa a tela com uma cor específica
        glClearColor(0.2f, 0.3f, 0.3f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);

        // Renderiza um triângulo
        glBegin(GL_TRIANGLES);
        // Define os vértices do triângulo
        glVertex2f(-0.5f, -0.5f);
        glVertex2f(0.0f, 0.5f);
        glVertex2f(0.5f, -0.5f);
        glEnd();

        // Troca os buffers da janela
        glfwSwapBuffers(window);
    }

    // Termina a GLFW
    glfwTerminate();
    return 0;
}
```
## Exemplo de Código de Shader

```glsl
#version 330 core // Define a versão do GLSL que estamos utilizando e o perfil core

// Atributo de posição do vértice (entrada)
layout(location = 0) in vec3 aPos;

// Variável para enviar as coordenadas dos vértices para o fragment shader (saída)
out vec3 vertexColor;

void main() {
    // Define a posição final do vértice
    gl_Position = vec4(aPos.x * 0.5, aPos.y * 0.5, aPos.z, 1.0);

    // Define a cor do vértice para enviar ao fragment shader (a cor será verde)
    vertexColor = vec3(0.0, 1.0, 0.0);
}
```
## Exemplo de Aplicação que Usa a OpenGL

Um exemplo de aplicação que usa a OpenGL é o Blender, um software de modelagem 3D e animação. O Blender usa a OpenGL para renderizar gráficos 3D em tempo real, permitindo aos artistas visualizar suas cenas e modelos em 3D. A integração da OpenGL permite ao Blender aproveitar o poder do hardware gráfico para renderizar gráficos complexos e detalhados.

## Referências

- [OpenGL - Wikipedia](https://en.wikipedia.org/wiki/OpenGL)
- [OpenGL Shading Language - Wikipedia](https://en.wikipedia.org/wiki/OpenGL_Shading_Language)
- [GLFW - The OpenGL Framework](https://www.glfw.org/)
- [GLEW - The OpenGL Extension Wrangler Library](http://glew.sourceforge.net/)
- [Blender - Official Website](https://www.blender.org/)
