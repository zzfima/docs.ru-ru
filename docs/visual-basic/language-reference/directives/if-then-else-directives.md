---
title: '#Директивы If…Then…#Else'
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
ms.openlocfilehash: 40e93b718241c9819e3c0fd84595e76eb0c86472
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343817"
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
Завершает блок оператора `#If`.

## <a name="remarks"></a>Заметки

На поверхности поведение директив `#If...Then...#Else` выглядит так же, как и инструкции `If...Then...Else`. Однако директивы `#If...Then...#Else` оценивают, что компилируется компилятором, в то время как инструкции `If...Then...Else` оценивают условия во время выполнения.

Условная компиляция обычно используется для компиляции одной и той же программы для разных платформ. Он также используется для предотвращения появления отладочного кода в исполняемом файле. Код, исключенный во время условной компиляции, полностью опускается из финального исполняемого файла, поэтому он не влияет на размер и производительность.

Независимо от результата вычисления все выражения оцениваются с помощью `Option Compare Binary`. Инструкция `Option Compare` не влияет на выражения в инструкциях `#If` и `#ElseIf`.

> [!NOTE]
> Не существует однострочной формы директив `#If`, `#Else`, `#ElseIf`и `#End If`. Никакой другой код не может отображаться в той же строке, что и любая из директив.

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

В этом примере используется конструкция `#If...Then...#Else` для определения необходимости компиляции определенных инструкций.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>См. также

- [Директива #Const](../../../visual-basic/language-reference/directives/const-directive.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
