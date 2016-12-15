---
title: "Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта | Microsoft Docs"
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
  - "объявление объектных переменных"
  - "объектные переменные, объявление"
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объявите переменную [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md), указав `As Object` в [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  Чтобы присвоить объект такой переменной, поместите его перед знаком равенства \(`=`\) в операторе выражения или предложении инициализации.  
  
## Пример  
 В следующем примере объявляется переменная `Object`, которой присваивается текущий экземпляр.  
  
```  
  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Можно комбинировать объявление и присвоение с помощью инициализации переменной как части объявления.  Следующий пример эквивалентен предыдущему:  
  
```  
Dim thisObject As Object = "This is an Object"  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылка на пространство имен <xref:System>.  
  
-   Класс, структура или модуль, в которые будет помещен оператор `Dim`.  
  
-   Процедура, в которую будет помещен оператор присваивания.  
  
## См. также  
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Объявление переменных объектов](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)