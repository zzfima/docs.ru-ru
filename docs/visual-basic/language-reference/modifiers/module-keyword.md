---
title: "Module &lt;ключевое_слово&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.ModuleAttribute"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "блоки атрибутов, Module - ключевое слово"
  - "Module - ключевое слово"
  - "Module - модификатор"
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Module &lt;ключевое_слово&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что атрибут в начале исходного файла применяется к текущему модулю сборки.  
  
## Заметки  
 Многие атрибуты относятся к отдельным элементам программирования, таким, например, как класс или свойство.  Применяйте такой атрибут путем присоединения блока атрибута в угловых скобках \(`< >`\), непосредственно к оператору объявления.  
  
 Если атрибут принадлежит не только следующему элементу, но и ко всему текущему модулю сборки, поместите блок атрибута в начале исходного файла и определите атрибут с ключевым словом `Module`.  Если он применяется ко всей сборке, то можно использовать ключевое слово [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md).  
  
 Модификатор `Module` отличается от [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
## См. также  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)