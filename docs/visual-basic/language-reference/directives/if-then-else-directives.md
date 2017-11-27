---
title: "#<a name=\"ifthenelse-directives\"></a>If... Then... #Else директивы"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a>Директивы #If...Then...#Else
Условно компилирует выбранные блоки кода Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parts"></a>Части  
 `expression`  
 Требуется для `#If` и `#ElseIf` операторов в другом месте. Любое выражение, состоящее исключительно из константы условной компиляции, литералы и операторов, результатом которого является `True` или `False`.  
  
 `statements`  
 Требуется для `#If` инструкции блока, необязательно в другом месте. Строки кода Visual Basic или директивы компилятора компилируются, если значение выражения, результатом которого является `True`.  
  
 `#End If`  
 Завершает `#If` блока инструкций.  
  
## <a name="remarks"></a>Примечания  
 В рабочей области, поведение `#If...Then...#Else` директивы отображается одинаково как для `If...Then...Else` инструкций. Тем не менее `#If...Then...#Else` директивы оперируют компилятором, тогда как `If...Then...Else` операторов результат вычисления условия во время выполнения.  
  
 Условная компиляция обычно используется для компиляции того же кода для разных платформ. Оно также используется для предотвращения появления в исполняемом файле отладочного кода. Код, исключаемый при условной компиляции полностью исключается из окончательный исполняемый файл, поэтому не влияет на производительность или размер.  
  
 Независимо от результата любого вычисления, все выражения вычисляются с помощью `Option Compare Binary`. `Option Compare` Инструкции не влияет на выражения в `#If` и `#ElseIf` инструкции.  
  
> [!NOTE]
>  Ни в какой форме однострочный `#If`, `#Else`, `#ElseIf`, и `#End If` существует директивы. Никакой другой код могут отображаться на одной строке с любой из директивы.  
  
## <a name="example"></a>Пример  
 В этом примере используется `#If...Then...#Else` для определения, следует ли компилировать определенных операторов.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
