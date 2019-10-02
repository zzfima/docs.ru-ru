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
ms.openlocfilehash: c5357dca24b03ddd03779866019baf14175be992
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698550"
---
# <a name="ifthenelse-directives"></a>Директивы #If...Then...#Else
Условно компилирует выбранные блоки кода Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
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
 Требуется для инструкций `#If` и `#ElseIf`, необязательно в других местах. Любое выражение, состоящее исключительно из одной или нескольких условных констант компилятора, литералов и операторов, результатом вычисления которого является `True` или `False`.  
  
 `statements`  
 Требуется для блока инструкций `#If`, необязательно в других местах. Visual Basic строки программы или директивы компилятора, компилируемые, если связанное выражение имеет значение `True`.  
  
 `#End If`  
 Завершает блок инструкций `#If`.  
  
## <a name="remarks"></a>Примечания  
 На поверхности поведение директив `#If...Then...#Else` выглядит так же, как и в инструкциях `If...Then...Else`. Однако директивы `#If...Then...#Else` оценивают, что компилирует компилятор, тогда как `If...Then...Else` операторы оценивают условия во время выполнения.  
  
 Условная компиляция обычно используется для компиляции одной и той же программы для разных платформ. Он также используется для предотвращения появления отладочного кода в исполняемом файле. Код, исключенный во время условной компиляции, полностью опускается из финального исполняемого файла, поэтому он не влияет на размер и производительность.  
  
 Независимо от результата вычисления все выражения оцениваются с помощью `Option Compare Binary`. Оператор `Option Compare` не влияет на выражения в инструкциях `#If` и `#ElseIf`.  
  
> [!NOTE]
> Не существует однострочной формы директив `#If`, `#Else`, `#ElseIf` и `#End If`. Никакой другой код не может отображаться в той же строке, что и любая из директив. 

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
 В этом примере используется конструкция `#If...Then...#Else`, чтобы определить, следует ли компилировать определенные инструкции.  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
