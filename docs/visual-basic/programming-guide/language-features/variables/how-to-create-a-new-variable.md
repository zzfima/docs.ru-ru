---
title: "Практическое руководство. Создание новой переменной (Visual Basic) | Microsoft Docs"
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
  - "Dim - оператор"
  - "переменные [Visual Basic], создание"
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание новой переменной (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Переменная создается с помощью [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### Создание новой переменной  
  
1.  Объявите переменную в операторе `Dim`.  
  
    ```  
  
    Dim newCustomer  
    ```  
  
2.  Включите спецификации для характеристик переменной, такие как [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).  Дополнительные сведения см. в разделе [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Нет необходимости использовать ключевое слово `Dim` при использовании других ключевых слов в объявлении.  
  
3.  За спецификацией должно следовать имя переменной, которое должно удовлетворять правилам и соглашениям [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  Дополнительные сведения см. в разделе [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  За именем следует предложение [As](../../../../visual-basic/language-reference/statements/as-clause.md), указывающее тип данных переменной.  
  
    ```  
    Public Static newCustomer As Customer   
    ```  
  
     Если не определить тип данных, используется тип данных по умолчанию: `Object`.  
  
5.  После предложения `As` следует знак равенства \(`=`\), а за ним начальное значение переменной.  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] назначает указанное значение переменной при каждом выполнении инструкции `Dim`.  Если начальное значение не задано, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] назначает начальное значение по умолчанию для типа данных переменной при первом выполнении кода, содержащего инструкцию `Dim`.  
  
     Если переменная имеет ссылочный тип, можно создать экземпляр класса, добавив ключевое слово [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) в предложение `As`.  Если `New` не используется, начальное значение переменной равно [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Операторы](../../../../visual-basic/language-reference/statements/index.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md)