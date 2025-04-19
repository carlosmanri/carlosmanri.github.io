---
title: "Código Morse"
date: 2025-04-19T16:25:38+02:00
# weight: 1
# aliases: ["/first"]
tags: ["radio"]
author: "Carlos Manrique"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---



| **Letra/Número** | **Código Morse** |
|-------------------|------------------|
| A                 | .-              |
| B                 | -...            |
| C                 | -.-.            |
| D                 | -..             |
| E                 | .               |
| F                 | ..-.            |
| G                 | --.             |
| H                 | ....            |
| I                 | ..              |
| J                 | .---            |
| K                 | -.-             |
| L                 | .-..            |
| M                 | --              |
| N                 | -.              |
| O                 | ---             |
| P                 | .--.            |
| Q                 | --.-            |
| R                 | .-.             |
| S                 | ...             |
| T                 | -               |
| U                 | ..-             |
| V                 | ...-            |
| W                 | .--             |
| X                 | -..-            |
| Y                 | -.--            |
| Z                 | --..            |
| 1                 | .----           |
| 2                 | ..---           |
| 3                 | ...--           |
| 4                 | ....-           |
| 5                 | .....           |
| 6                 | -....           |
| 7                 | --...           |
| 8                 | ---..           |
| 9                 | ----.           |
| 0                 | -----           |


## Como árbol binario

El código Morse puede representarse como un árbol binario, donde cada nodo representa una letra o número. Las decisiones en el árbol dependen del carácter Morse:

- Un punto (.) significa moverse al hijo izquierdo.
- Un guion (-) significa moverse al hijo derecho.


                (Inicio)
                /     \
             .          -
            E            T
          /   \        /   \
         I     A      N     M
        / \   / \    / \   / \
       S   U R   W  D   K G   O

Este tipo de estructura es útil para decodificar el código Morse, ya que cada paso en el árbol guía directamente al carácter correspondiente. 

## Criterio de ordenación

El orden de las letras en el árbol de código Morse no es arbitrario; sigue un criterio basado en la frecuencia de uso de las letras en inglés. Este diseño tiene como objetivo hacer que las letras más comunes tengan los códigos más cortos en términos de puntos (.) y guiones (-). Esto optimiza la comunicación en el sistema de telegrafía Morse.


- Letras más comunes tienen códigos más cortos:
        E (.) y T (-) son las letras más frecuentes en inglés, por lo que están en el primer nivel del árbol y tienen los códigos más cortos posibles.
        Esto reduce el tiempo necesario para transmitir las letras más usadas.

- Letras menos frecuentes tienen códigos más largos:
        Las letras que aparecen menos frecuentemente, como Q, Z, o Y, están más abajo en el árbol y requieren combinaciones más largas de puntos y guiones.

- Equilibrio en la navegación del árbol:
        El diseño del árbol intenta mantener un equilibrio lógico en el acceso a las letras. Si bien algunas ramas pueden ser más profundas que otras debido a la frecuencia de los caracteres, se procura que las combinaciones sigan un patrón fácil de recordar.