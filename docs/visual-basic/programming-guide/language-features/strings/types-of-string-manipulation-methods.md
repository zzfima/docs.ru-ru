---
title: "Типы методов для работы со строками в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "управление строками"
  - "строки [Visual Basic], управление [Visual Basic]"
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы методов для работы со строками в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Существуют несколько способов анализа и работы со строками.  Некоторые методы являются частью языка [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], в то время как другие принадлежат классу `String`.  
  
## Язык Visual Basic и .NET Framework  
 Методы [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] используются как встроенные функции языка.  Они могут применяться без уточнения в коде.  В следующем примере показано использование обычной команды управления строкой в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]:  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 В этом примере функция `Mid` выполняет прямую операцию над `aString` и назначает значение для `bString`.  
  
 Перечень методов Visual Basic для работы со строками см. в разделе [Сводка по работе со строками](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).  
  
### Общие методы и методы экземпляра  
 Строками можно управлять и с помощью методов класса `String`.  В классе `String` есть два типа методов: *общие методы* и методы *экземпляра*.  
  
#### Общие методы  
 Общий метод реализован непосредственно в классе `String`, и для его работы не требуется существования экземпляра данного класса.  Эти методы определяются именем класса \(`String`\), а не экземпляра класса `String`.  Примеры.  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 В предыдущем примере метод <xref:System.String.Copy%2A?displayProperty=fullName> является статическим. Он обрабатывает заданное выражение и присваивает итоговое значение строке `bString`.  
  
#### Методы экземпляра  
 Напротив, методы экземпляра основываются на отдельном экземпляре `String` и должны уточняться именем экземпляра.  Примеры.  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 В этом примере метод <xref:System.String.Substring%2A?displayProperty=fullName> является методом экземпляра `String` \(то есть `aString`\).  Он выполняет операцию над `aString` и присваивает это значение `bString`.  
  
 Дополнительные сведения см. в документации по классу <xref:System.String>.  
  
## См. также  
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)