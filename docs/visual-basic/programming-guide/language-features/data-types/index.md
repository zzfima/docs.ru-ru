---
title: "Типы данных в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "типы данных [Visual Basic], объявление"
  - "типизация"
  - "типы данных [Visual Basic]"
  - "код Visual Basic, типы данных"
  - "типы данных [Visual Basic], ускорение с помощью"
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Типы данных в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*Тип данных* программного элемента определяет данные, которые могут содержаться в нем, и способы их хранения.  Типы данных применяются ко всем значениям, которые могут храниться в памяти компьютера или участвовать в вычислении выражения.  Каждая переменная, литерал, константа, перечисление, свойство, параметр процедуры, аргумент процедуры и возвращаемое значение процедуры имеют тип данных.  
  
## Объявленные типы данных  
 При определении программного элемента при помощи оператора объявления нужно указать тип данных с помощью предложения `As`.  В следующей таблице представлены операторы, используемые для объявления различных элементов.  
  
|Программный элемент|Объявление типов данных|  
|-------------------------|-----------------------------|  
|Переменная|В [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)<br /><br /> `Dim`   `amount As Double`<br /><br /> `Static`   `yourName As String`<br /><br /> `Public`   `billsPaid As Decimal = 0`|  
|Literal|Для символьного типа литерала см. раздел "Символьные типы литерала" [Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)<br /><br /> `Dim searchChar As Char = "."`  `C`|  
|Константа|В [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)<br /><br /> `Const`   `modulus As Single = 4.17825F`|  
|Перечисление|В [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)<br /><br /> `Public`   `Enum`   `colors`|  
|Свойство|В [Оператор Property](../../../../visual-basic/language-reference/statements/property-statement.md)<br /><br /> `Property`   `region() As String`|  
|Параметр процедуры|В [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md), [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Sub addSale(ByVal`   `amount`   `As Double)`|  
|Аргумент процедуры|В вызывающем коде вызова каждый аргумент является программным элементом, который уже был объявлен, или выражением, содержащим объявленные элементы<br /><br /> `subString = Left(`  `inputString`  `,`   `5`  `)`|  
|Возвращаемое значение процедуры|В [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) или [Оператор Operator](../../../../visual-basic/language-reference/statements/operator-statement.md)<br /><br /> `Function convert(ByVal b As Byte)`   `As String`|  
  
 Список типов данных Visual Basic см. в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
## См. также  
 [Символы типов](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Простые типы данных](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Составные типы данных](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Преобразование типов в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Структуры](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Устранение неполадок, связанных с типами данных](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Эффективное использование типов данных](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)