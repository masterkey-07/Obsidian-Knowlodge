#raw

O [vídeo](https://www.youtube.com/watch?v=C8YtdC8mxTU) aborda o pipeline de renderização gráfica em videogames, explicando como bilhões de bits processados pela GPU transformam dados em gráficos 3D realistas. Ele foca nos três passos principais desse processo: **Sombreamento de Vértices**, **Rasterização**, e **Sombreamento de Fragmentos**.

## **Sombreamento de Vértices**

Transforma objetos tridimensionais em coordenadas de tela 2D. Cada vértice passa por transformações matemáticas que posicionam os triângulos na tela. Um exemplo dado é a locomotiva de *Red Dead Redemption 2*, composta por 762 mil triângulos.

## **Rasterização**

Converte os triângulos em fragmentos, que são grupos de pixels. A GPU calcula quais pixels pertencem a cada triângulo e aplica texturas ou cores.

**Problema de Profundidade**

Sobre a rasterização, é apresentado o problema de profundidade, ao qual envolve como renderizar vários elementos ao qual um pode estar na frente do outro, para resolver isso é apresentado técnicas como calcular a posição Z de cada pixel e priorizar aqueles que tem o maior valor. 

**Anti-Aliasing por Superamostragem**

É uma técnica de suavização de pontas, a partir de manipulação da intensidade das cores das bordas dos triangulos.

## **Sombreamento de Fragmentos**

Determina a cor final de cada pixel com base na iluminação, sombra e reflexos, tornando o visual mais realista. O vídeo exemplifica como a luz afeta o sombreado de um objeto, ajustando as cores de acordo com a direção da luz.

**Sombreamento Suave**

Utilizando as normais dos vertices, misturando as cores dos 3 vertices com coordenadas baricêntricas, ao qual aplica um efeito de mistura de core sobre o sombreamento. 

# Outros conceitos abordados

## **Ray Tracing**

Aplicado para criar cenas com alto realismo simulando iluminação, reflexos e sombras realistas.

## **DLSS - Deep Learning Super Sampling**

Utilizando de uma rede neural convolucional, ele amplifica uma imagem Full HD para 4K.