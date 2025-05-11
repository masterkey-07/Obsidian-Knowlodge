[[Computer Graphics]] Topic

#raw 

# O que é Ray Tracing?

O vídeo começa introduzindo o conceito de **Ray** e **Ray Casting**, onde um **Ray** (raio) é definido por uma origem e uma direção, enquanto **Ray Tracing** se refere ao processo de determinar onde o raio irá atingir. Também é comentado que, com **Ray Casting**, é possível gerar sombras em um ponto caso haja algum objeto entre o ponto de origem e o ponto de destino.

Para explicar o que é **Ray Tracing** na prática, o vídeo apresenta a história do desenvolvimento dessa técnica.

Começando em 1980, é mostrado o algoritmo clássico de **Ray Tracing**, no qual, para cada pixel na tela, um raio é "enviado" para a cena. Para cada interseção do raio com objetos, outros raios são enviados para calcular sombras e luzes. Com isso, a cor que deve ser apresentada no pixel é composta a partir dessas interações. Em resumo, para cada superfície, um raio é disparado.

Em 1984, o vídeo apresenta o **Cook Stochastic ("Distribution") Ray Tracing**, no qual, ao invés de enviar um único raio por superfície, são enviados vários raios para pintar o pixel de forma mais complexa, levando em consideração os diferentes raios que atingem um ponto de uma superfície.

Por fim, em 1986, é apresentada a técnica de **Kajiya-Style Diffuse Interreflection**, na qual, para cada superfície, vários raios são disparados em direção a outros objetos, acumulando as reflexões com base nas interações entre diferentes superfícies.

# Rasterização vs Ray Tracing

O vídeo aborda fundamentalmente as diferenças entre **Rasterization** e **Ray Tracing**. Na **Rasterização**, o processo itera sobre cada objeto para determinar qual está mais próximo de cada pixel. Já no **Ray Tracing**, para cada pixel, itera-se sobre cada objeto para descobrir qual está mais perto.

O benefício do **Ray Tracing** quando a imagem é maior vem de uma técnica chamada **Bounding Volume Hierarchy (BVH)**. Essa técnica cria uma estrutura hierárquica de objetos na cena, agrupando elementos sob nós que representam áreas maiores. Com essa estrutura, é possível otimizar a busca, economizando iterações sobre os elementos, pois é uma pesquisa em árvore ao invés de percorrer uma lista completa. Se o objeto raiz maior não for atingido por um raio, já se pode calcular o próximo raio disparado, sem precisar verificar todos os itens individualmente.

Apesar de ambos os métodos terem seus pontos fortes e fracos, o ponto final é entender quando aplicar cada técnica e como utilizar ambas para construir cenas de forma eficiente.

# Ray Tracing Hardware

Neste vídeo, é discutido como o problema de **Ray Tracing** é altamente paralelo e explora as tecnologias de hardware físico utilizadas para lidar com esses desafios.

O vídeo começa falando sobre os **RT Cores**, que realizam duas operações principais:

- **Ray-bounding volume hierarchy (BVH) traversal**: Retorna as caixas que foram atingidas pelo raio.
- **Ray-Triangle Intersection**: Retorna os triângulos atingidos pelo raio.

Essas operações são aplicadas a várias funções, como sombreamento, interseções customizadas e instanciamento em múltiplos níveis.

Após a apresentação sobre os **RT Cores**, o vídeo aborda o aumento da memória RAM nas GPUs e como isso influencia a performance do **Ray Tracing** e outras operações gráficas.

No fim, mostra a evolução das técnologias utilizando combinações de técnicas para realizar as operações gráficas.

# The Ray Tracing Pipeline

Neste vídeo, é discutido como o **Ray Tracing** é uma técnica de renderização altamente paralela e explora as novas funcionalidades introduzidas para acelerar esse processo.

São apresentados os cinco novos tipos de shaders introduzidos para Ray Tracing no DirectX:

- **Ray Generation Shader**: Gerencia o processo de ray tracing.
- **Intersection Shader**: Define a forma dos objetos.
- **Miss Shader**: Lida com raios que não atingem nenhum objeto.
- **Closest Hit Shader**: Processa o ponto de impacto mais próximo.
- **Any Hit Shader**: Usado para objetos transparentes.

O vídeo então explica o fluxo básico do pipeline de ray tracing, desde a geração do raio até a determinação da cor final do pixel.

São mostradas aplicações práticas do ray tracing em tempo real:

- Jogos: Para reflexões, iluminação global e sombras.
- Baking mais rápido: Redução drástica no tempo de processamento.
- Teste de ground truth: Para validar aproximações de shaders.

Por fim, o vídeo menciona possíveis usos não convencionais do hardware de ray tracing, como detecção de colisão e renderização volumétrica, indicando um campo aberto para pesquisas e inovações.

# Ray Tracing Effects

Neste vídeo, são discutidos os diversos **efeitos de Ray Tracing** e como eles contribuem para criar imagens realistas em computação gráfica.

O vídeo começa com uma comparação entre uma foto real e uma simulação da famosa **Cornell Box**, demonstrando o realismo alcançável com ray tracing.

São apresentados vários efeitos de ray tracing:

1. **Sombras duras**: Produzidas por fontes de luz pontuais.
2. **Sombras suaves**: Geradas por fontes de luz de área, criando penumbras.
3. **Iluminação global**: Inclui inter-reflexão, iluminação indireta e sangramento de cor.
4. **Reflexões glossy**: Criando reflexos mais suaves e realistas.
5. **Oclusão de ambiente**: Simulando sombras em áreas ocluídas, mesmo sem fonte de luz específica.
6. **Profundidade de campo**: Criando desfoque de fundo ou primeiro plano para efeitos cinematográficos.
7. **Motion blur**: Simulando o borrão de movimento em objetos em alta velocidade.
8. **Efeitos atmosféricos**: Como feixes de luz visíveis no ar.
9. **Cáusticas**: Padrões de luz criados por reflexão ou refração em superfícies como água ou vidro.

O vídeo apresenta exemplos visuais de cada efeito, incluindo uma demonstração do Minecraft RTX com ray tracing.

# The Rendering Equation

Neste vídeo, é discutida a **Equação de Renderização**, uma ferramenta fundamental para entender como a luz se comporta em computação gráfica.

O vídeo começa explicando a importância da equação de renderização e seus componentes principais:

1. **Ponto X**: Um ponto na cena.
2. **Direção de saída (Ω_o)**: A direção para onde a luz está indo (por exemplo, em direção ao olho).
3. **Direção de entrada (Ω_i)**: A direção de onde a luz está vindo.
4. **Normal da superfície**: A direção perpendicular à superfície no ponto X.
5. **Integral sobre todas as direções de entrada**.

A equação é composta por:
- **Luz emitida**: Luz proveniente diretamente de fontes luminosas.
- **Luz refletida**: Combinação de luz incidente, propriedades do material e termo geométrico (Lei do cosseno de Lambert).

O vídeo então explica o **Path Tracing**, uma técnica que implementa a equação de renderização:

- Raios são disparados do olho e ricocheteiam na cena.
- A equação é aplicada recursivamente em cada ponto de interseção.

São apresentadas técnicas para melhorar a eficiência do path tracing:

1. **Amostragem por Importância**: Direciona raios para direções mais relevantes com base nas propriedades do material (BSDF - Função de Distribuição de Espalhamento Bidirecional).
2. **Amostragem por Importância Múltipla**: Combina amostragem baseada no material e nas fontes de luz.

O vídeo mostra exemplos visuais de como diferentes materiais (espelho, vidro, superfícies difusas) afetam a distribuição dos raios.

Por fim, é apresentado um exemplo prático da aplicação de path tracing no jogo Quake II, demonstrando como a técnica pode melhorar significativamente a qualidade visual de um jogo antigo.

# Denoising for Ray Tracing

Neste vídeo, é discutido o processo de **Denoising** (redução de ruído) em ray tracing, uma técnica fundamental para melhorar a qualidade das imagens renderizadas.

"Ruídos" em imagens criadas por **Ray Tracing**, aparecem quando são usados poucos **Raios** para montar a cor do pixel em relação a cena. Por padrão, esse desafio pode ser resolvido aumentando a quantidade de **Raios** disparados, o lado negativo disso é o aumento na computação, porém, usando de **Denoising**, é possível suavizar o efeito usando de técnicas que variam de modalagens matemáticas a utilização de inteligência artificial.

Com essa técnica, é possível utilizar **Ray Tracing** com poucos **Raios** disparados por pixel (samples per pixel), evitando alto custo computacional enquanto entrega imagens com ótima qualidade.