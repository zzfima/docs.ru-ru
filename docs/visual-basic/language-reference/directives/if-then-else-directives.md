---
title: '#If... Then... #Else директивы'
ms.date: 04/11/2018
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69ce56d770de5f004f204b1764fd51d948ba92c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591085"
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

Операторы в блоке условной компиляции должен быть полный логических операторов. Например нельзя условной компиляции только атрибуты функции, но можно условно Объявите функцию и ее атрибуты:

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>Пример
 В этом примере используется `#If...Then...#Else` для определения, следует ли компилировать определенных операторов.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>См. также  
[Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)  
[Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


