---
title: "Директивы #If...Then...#Else | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.#EndIf"
  - "#End If"
  - "#Then"
  - "#ElseIf"
  - "vb.#ElseIf"
  - "vb.#Else"
  - "vb.#If"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#Else - директива [Visual Basic]"
  - "#End if - директива [Visual Basic]"
  - "#If - директива [Visual Basic]"
  - "условная компиляция, директивы"
  - "else - директива (#else)"
  - "выборочная компиляция"
  - "код Visual Basic, компиляция"
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Директивы #If...Then...#Else
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Условно компилирует выбранные блоки кода Visual Basic.  
  
## Синтаксис  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## Части  
 `expression`  
 Обязательный параметр для операторов `#If` `#ElseIf`. Необязательный параметр в других случаях.  Любое выражение, состоящее исключительно из одной или более константы условной компиляции, литеральных выражений и операторов, результат вычисления которого равен `True` или `False`.  
  
 `statements`  
 Обязательный параметр в блоке оператора `#If`. Необязательный параметр в других случаях.  Строки кода или директивы компилятора Visual Basic компилируются, если значение выражения вычисляется как `True`.  
  
 `#End If`  
 Завершает блок оператора `#If`.  
  
## Заметки  
 Внешне принцип действия директив `#If...Then...#Else` аналогичен принципу действия операторов `If...Then...Else`.  Однако директивы `#If...Then...#Else` оперируют с компилируемым кодом, тогда как операторы `If...Then...Else` вычисляют условия во время выполнения.  
  
 Обычно условная компиляция используется для компиляции одного и того же кода для разных платформ.  Также она используется для предотвращения появления отладочного кода в исполняемом файле.  Код, исключаемый при условной компиляции, полностью исключается из результирующего исполняемого файла, в результате чего он не влияет на производительность или размер.  
  
 Вне зависимости от результата любого вычисления все выражения оцениваются с помощью `Option Compare Binary`.  Оператор `Option Compare` не влияет на выражения в операторах `#If` и `#ElseIf`.  
  
> [!NOTE]
>  Однострочной формы `#If`, `#Else`, `#ElseIf` и `#End If` не существует.  Не допускается ввод кода на строке, на которой присутствует директива.  
  
## Пример  
 В данном примере конструкция `#If...Then...#Else` используется для определения необходимости компиляции определенных частей кода.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## См. также  
 [Директива \#Const](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)