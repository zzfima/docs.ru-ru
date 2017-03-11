---
title: "Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic | Microsoft Docs"
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
  - "StringBuilder - класс"
  - "строки [Visual Basic], использование класса StringBuilder"
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

В этом примере создается длинная строка из множества маленьких строк с помощью класса <xref:System.Text.StringBuilder>.  Класс <xref:System.Text.StringBuilder> является более эффективным для сложения нескольких строк, чем оператор `&=`.  
  
## Пример  
 В следующем примере создается экземпляр класса <xref:System.Text.StringBuilder>, прибавляется 1 000 строк к этому экземпляру и возвращается его строковое представление.  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-to-create-strings-us_1.vb)]  
  
## См. также  
 [Использование класса StringBuilder](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)   
 [Оператор &\=](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)   
 [Строки](../../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Создание новых строк](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Обработка строк](../Topic/Manipulating%20Strings%20in%20the%20.NET%20Framework.md)   
 [Strings Sample](http://msdn.microsoft.com/ru-ru/be9e82a3-dc95-4aaa-9396-61b66e467e02)