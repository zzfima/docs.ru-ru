---
title: "Практическое руководство: сворачивание и скрытие частей кода (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 200a90b6983277d46b6e5c7b27ee4a90ecf88c40
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a>Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)
`#Region` Директива позволяет Сворачивание и скрытие частей кода в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] файлов. `#Region` Директива позволяет указать блок кода, который можно разворачивать и сворачивать при использовании [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] редактора кода. Возможность избирательно прятать код делает файлы более управляемыми и легче читать. Дополнительные сведения см. в разделе [Структура](https://docs.microsoft.com/visualstudio/ide/outlining).  
  
 `#Region`директивы поддерживают семантики блока кода, например `#If...#End If`. Это значит, они не может начинаться в одном блоке и заканчиваться в другом; Начало и конец должны быть в одном блоке. `#Region`директивы не поддерживаются внутри функций.  
  
### <a name="to-collapse-and-hide-a-section-of-code"></a>Чтобы свернуть и спрятать раздел кода  
  
-   Поместите раздел кода между `#Region` и `#End Region` операторы, как показано в следующем примере:  
  
     [!code-vb[VbVbalrConditionalComp №&6;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/how-to-collapse-and-hide-sections-of-code_1.vb)]  
  
     `#Region` Блок может использоваться несколько раз в файле кода; таким образом, пользователи могут определять свои собственные блоки процедур и классов, которые в свою очередь, можно свернуть. `#Region`блоки также могут быть вложены в другие `#Region` блоков.  
  
    > [!NOTE]
    >  Скрытие кода не препятствует его компиляции и не влияет на `#If...#End If` инструкции.  
  
## <a name="see-also"></a>См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md)   
 [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Структура](https://docs.microsoft.com/visualstudio/ide/outlining)
