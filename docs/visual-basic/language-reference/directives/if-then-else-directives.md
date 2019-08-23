---
title: '#Если... Then... #Else директивы (Visual Basic)'
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
ms.openlocfilehash: 697521276e2d5a8d0a4aaae38789a21b7aa87fcb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940759"
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
 Требуется для `#If` операторов `#ElseIf` и, необязательно в других местах. Любое выражение, состоящее только из одной или нескольких условных констант компилятора, литералов и операторов, которые имеют значение `True` или. `False`  
  
 `statements`  
 Требуется для `#If` блока инструкций, необязательно в других местах. Visual Basic строки программы или директивы компилятора, компилируемые, если связанное выражение имеет значение `True`.  
  
 `#End If`  
 Завершает блок операторов `#If` .  
  
## <a name="remarks"></a>Примечания  
 На поверхности поведение `#If...Then...#Else` директив выглядит так же, как `If...Then...Else` и инструкции. Однако директивы оценивают, что компилирует компилятор, тогда как `If...Then...Else` инструкции оценивают условия во время выполнения. `#If...Then...#Else`  
  
 Условная компиляция обычно используется для компиляции одной и той же программы для разных платформ. Он также используется для предотвращения появления отладочного кода в исполняемом файле. Код, исключенный во время условной компиляции, полностью опускается из финального исполняемого файла, поэтому он не влияет на размер и производительность.  
  
 Независимо от результата вычисления все выражения вычисляются с помощью `Option Compare Binary`. Инструкция не влияет на выражения в `#If` операторах `#ElseIf`и. `Option Compare`  
  
> [!NOTE]
> Не существует `#If`однострочной формы директив, `#Else`, `#ElseIf`и. `#End If` Никакой другой код не может отображаться в той же строке, что и любая из директив. 

Инструкции в блоке условной компиляции должны быть полными логическими операторами. Например, невозможно условно компилировать только атрибуты функции, но можно условно объявить функцию вместе с ее атрибутами:

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
 В этом примере `#If...Then...#Else` конструкция используется для определения необходимости компиляции определенных инструкций.  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
