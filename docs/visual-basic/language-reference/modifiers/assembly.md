---
title: "Assembly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Assembly"
  - "vb.AssemblyAttribute"
  - "Assembly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Assembly - ключевое слово"
  - "Assembly - модификатор"
  - "блоки атрибутов, Assembly - ключевое слово"
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Assembly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Определяет, что атрибут в начале файла исходного кода применим ко всей сборке.  
  
## Заметки  
 Многие атрибуты относятся к отдельным элементам программирования, таким, например, как класс или свойство.  Применяйте такой атрибут путем присоединения блока атрибута в угловых скобках \(`< >`\), непосредственно к оператору объявления.  
  
 Если атрибут принадлежит не только к следующему элементу, но и ко всей сборке, поместите блок атрибута в начале исходного файла и определите атрибут ключевым словом `Assembly`.  Если он применяется к текущему модулю сборки, используйте ключевое слово [Модуль](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 Можно также применить атрибут к сборке в файле AssemblyInfo.vb, в этом случае нет необходимости использовать блок атрибутов в файле главного исходного кода.  
  
## См. также  
 [Module \<ключевое\_слово\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)