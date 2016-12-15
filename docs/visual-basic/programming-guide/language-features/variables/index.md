---
title: "Переменные в Visual Basic | Microsoft Docs"
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
  - "значения [Visual Basic], хранение"
  - "переменные [Visual Basic]"
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменные в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

При выполнении вычислений в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] часто приходится сохранять значения.  Например, может возникнуть необходимость вычислить несколько значений, сравнить их и выполнить некоторые операции над ними в зависимости от результатов сравнения.  Необходимо сохранить значения, если их нужно сравнить.  
  
## Использование  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], как и большинство языков программирования, использует переменные для хранения значений.  У *переменной* есть имя \(слово, которое будет использоваться для ссылки на значение, которое содержит переменную\).  Переменная также имеет тип данных \(который определяет тип данных, которые можно хранить в переменной\).  Переменная может представлять массив, если необходимо хранить индексированную последовательность связанных элементов данных.  
  
 Вывод локального типа позволяет объявлять переменные без явного указания типа данных.  Компилятор определяет тип данных переменной из типа выражения, которое ее инициализирует.  Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## Назначение значений  
 Операторы присваивания используются для выполнения вычислений и для присвоения результата переменной, как показано в следующем примере.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Знак равенства \(`=`\) в этом примере является оператором присвоения, а не оператором равенства.  Значение присваивается переменной `applesSold`.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## Переменные и свойства  
 Значение , если элемент входит в коллекцию; в противном случае — значение .  Тем не менее, оно является более сложным, чем переменная.  Свойство использует блоки кода, определяющие, как задавать и извлекать его значение.  Дополнительные сведения см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## См. также  
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Устранение неполадок, связанных с переменными](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)   
 [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)