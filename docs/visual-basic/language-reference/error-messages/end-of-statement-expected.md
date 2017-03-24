---
title: "Ожидается окончание оператора | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30205"
  - "vbc30205"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30205"
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Ожидается окончание оператора
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Оператор является синтаксически завершенным, однако за элементом, завершающим оператор, следует дополнительный программный элемент.  В конце каждого оператора требуются признаки конца строки.  
  
 Терминатор линии делит символы файла источника Visual Basic в линии.  Примеры терминаторов линии символ возврата каретки юникода \(&HD\), символ перевода строки юникода \(&HA\) и символ возврата каретки юникода, за которым следует символ перевода строки юникода.  Дополнительные сведения о терминаторах линии см. в разделе [Спецификация языка Visual Basic](../../../visual-basic/reference/language-specification.md).  
  
 **Идентификатор ошибки:** BC30205  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте, не помещены ли случайно два разных оператора на одну строку.  
  
2.  Вставьте признак конца строки после элемента, завершающего оператор.  
  
## См. также  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)   
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)