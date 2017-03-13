---
title: "Директива #Region | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Region"
  - "vb.#Region"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#region - директива"
  - "#Region - ключевое слово"
  - "region - директива (#region)"
  - "компилятор Visual Basic, директивы компилятора"
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Директива #Region
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Сворачивает и скрывает разделы кода в файлах Visual Basic.  
  
## Синтаксис  
  
```  
  
        #Region "identifier_string"  
#End Region  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`identifier_string`|Обязательный.  Строка, которая выступает в качестве заголовка области, если он свернут.  По умолчанию области свернуты.|  
|`#End Region`|Завершает блок `#Region`.|  
  
## Заметки  
 Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio.  Области можно размещать или *вкладывать* в другие области для группировки с похожими областями.  
  
## Пример  
 В этом примере используется директива `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## См. также  
 [Директивы \#If...Then...\#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Структура](/visual-studio/ide/outlining)   
 [Практическое руководство. Сворачивание и сокрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)