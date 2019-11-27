---
title: Практическое руководство. Сворачивание и сокрытие частей кода
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: e7aacdc3f41199127b00d276b382ec4a5f258da0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347411"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)

Директива `#Region` позволяет сворачивать и скрывать разделы кода в файлах Visual Basic. Директива `#Region` позволяет указать блок кода, который можно развернуть или свернуть при использовании редактора кода Visual Studio. Возможность скрывать код выборочно делает файлы более управляемыми и удобочитаемыми. Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).

директивы `#Region` поддерживают семантику блока кода, например `#If...#End If`. Это означает, что они не могут начинаться в одном блоке и заканчиваться другим; Начало и конец должны находиться в одном блоке. директивы `#Region` не поддерживаются в функциях.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Сворачивание и скрытие раздела кода

Разместите раздел кода между инструкциями `#Region` и `#End Region`, как показано в следующем примере:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Блок `#Region` можно использовать несколько раз в файле кода. Таким же пользователь может определить собственные блоки процедур и классов, которые, в свою очередь, можно свернуть. блоки `#Region` также могут быть вложены в другие блоки `#Region`.

> [!NOTE]
> Скрытие кода не мешает его компиляции и не влияет на `#If...#End If` инструкции.

## <a name="see-also"></a>См. также

- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Структура](/visualstudio/ide/outlining)
