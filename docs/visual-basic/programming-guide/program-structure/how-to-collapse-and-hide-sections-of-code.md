---
title: Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c02e95573d0ba894bf68510219bd66965fc234fc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)
`#Region` Директива позволяет Сворачивание и скрытие частей кода в файлах Visual Basic. `#Region` Директива позволяет указать блок кода, который можно разворачивать и сворачивать при использовании [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] редактора кода. Возможность выборочно скрывать участки кода делает файлы, управляемость и облегчает чтение. Дополнительные сведения см. в разделе [Структура](/visualstudio/ide/outlining).  
  
 `#Region` директивы поддерживают семантики блока кода, такие как `#If...#End If`. Это означает, не могут начинаться в одном блоке или заканчиваться в другом; Начало и конец должны быть в одном блоке. `#Region` директивы внутри функции не поддерживаются.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Сворачивание и скрытие раздела кода  
  
-   Поместите раздел кода между `#Region` и `#End Region` инструкции, как показано в следующем примере:  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     `#Region` Блок может использоваться несколько раз в файле кода; таким образом, пользователи могут определять свои собственные блоки процедур и классов, которые в свою очередь, можно свернуть. `#Region` блоки, также могут быть вложены в другие `#Region` блоков.  
  
    > [!NOTE]
    >  Скрытие кода не препятствует его компиляции и не влияет на `#If...#End If` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Структура](/visualstudio/ide/outlining)
