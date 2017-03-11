---
title: "Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "код Visual Basic, свертывание и скрытие"
  - "Visual Basic, свертывание кода"
  - "Visual Basic, скрытие кода"
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Сворачивание и скрытие частей кода (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Директива `#Region` позволяет сворачивать и скрывать разделы кода в файлах [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Деректива `#Region` позволяет указать блок кода, который можно разворачивать и сворачивать при использовании редактора кода [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  Возможность избирательно прятать код делает файлы более управляемыми и их проще читать.  Дополнительные сведения см. в разделе [Структура](/visual-studio/ide/outlining).  
  
 Директивы `#Region` поддерживают семантики блока кода, например, `#If...#End If`.  Это означает, что они не могут начинаться в одном блоке и заканчиваться в другом; начало и конец должны быть в одном блоке.  Директивы `#Region` не поддерживаются внутри функций.  
  
### Чтобы свернуть и спрятать раздел кода проделайте следующие действия  
  
-   Поместите раздел кода между инструкциями `#Region` и `#End Region`, как показано в следующем примере.  
  
     [!code-vb[VbVbalrConditionalComp#6](../../../visual-basic/language-reference/directives/codesnippet/visualbasic/how-to-collapse-and-hide_1.vb)]  
  
     Блок `#Region` может использоваться несколько раз в файле кода; таким образом пользователи могут определять свои собственные блоки процедур и классов, которые, в свою очередь, можно свернуть.  Блоки `#Region` также могут быть вложены в другие блоки `#Region`.  
  
    > [!NOTE]
    >  Скрытие кода не препятствует его компиляции и не влияет на инструкции `#If...#End If`.  
  
## См. также  
 [Условная компиляция](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
 [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md)   
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Структура](/visual-studio/ide/outlining)