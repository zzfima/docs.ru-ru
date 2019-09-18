---
title: Практическое руководство. Сворачивание и скрытие разделов кода (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: 4f11982cc0aa7654c1e456fb15d918a68bc4791b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054121"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Практическое руководство. Сворачивание и скрытие разделов кода (Visual Basic)

`#Region` Директива позволяет сворачивать и скрывать разделы кода в файлах Visual Basic. `#Region` Директива позволяет указать блок кода, который можно развернуть или свернуть при использовании редактора кода Visual Studio. Возможность скрывать код выборочно делает файлы более управляемыми и удобочитаемыми. Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).

`#Region`директивы поддерживают семантику блока кода, такую `#If...#End If`как. Это означает, что они не могут начинаться в одном блоке и заканчиваться другим; Начало и конец должны находиться в одном блоке. `#Region`директивы не поддерживаются в функциях.

## <a name="to-collapse-and-hide-a-section-of-code"></a>Сворачивание и скрытие раздела кода

Поместите раздел кода между `#Region` операторами и `#End Region` , как показано в следующем примере:

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

Этот `#Region` блок можно использовать несколько раз в файле кода, поэтому пользователи могут определять собственные блоки процедур и классов, которые, в свою очередь, могут быть свернуты. `#Region`блоки также могут быть вложены в `#Region` другие блоки.

> [!NOTE]
> Скрытие кода не мешает его компиляции и не влияет на `#If...#End If` инструкции.

## <a name="see-also"></a>См. также

- [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)
- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Структура](/visualstudio/ide/outlining)
