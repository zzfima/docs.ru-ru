---
title: "Type Relationships in LINQ Query Operations (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "inferring type information [LINQ in C#]"
  - "data sources [LINQ in C#], type relationships"
  - "queries [LINQ in C#], type relationships"
  - "relationships [LINQ in C#]"
  - "type relationships [LINQ in C#]"
  - "variable relationships [LINQ in C#]"
  - "type information inferred [LINQ in C#]"
  - "data transformations [LINQ in C#]"
  - "LINQ [C#], type relationships"
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
caps.latest.revision: 25
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Type Relationships in LINQ Query Operations (C#)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Для эффективного написания запросов следует понимать, как типы переменных связаны друг с другом в полной операции запроса.  Понимание этих связей облегчит усвоение примеров [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] и примеров кода в документации.  Более того, можно будет представить, что происходит в фоновом режиме при неявном типизировании переменных с помощью `var`.  
  
 Операции запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] строго типизированы в источнике данных, в самом запросе и при выполнении запроса.  Тип переменных в запросе должен быть совместим с типом элементов в источнике данных и с типом переменной итерации в операторе `foreach`.  Строгая типизация гарантирует перехват ошибок во время компиляции, когда их можно будет исправить прежде, чем с ними столкнутся пользователи.  
  
 Для демонстрации связи типов большая часть примеров использует явную типизацию для всех переменных.  Последний пример показывает применение тех же принципов даже при использовании неявной типизации с помощью [var](../../../../csharp/language-reference/keywords/var.md).  
  
## Запросы, не выполняющие преобразование исходных данных  
 На следующем рисунке показана операция запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to Objects, не выполняющая преобразование данных.  Источник содержит последовательность строк, результат запроса также является последовательностью строк.  
  
 ![Отношения между типами данных в запросе LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_flow1.png "LINQ\_flow1")  
  
1.  Аргумент типа источника данных определяет тип переменной диапазона.  
  
2.  Тип выбранного объекта определяет тип переменной запроса.  Здесь `name` является строкой.  Следовательно, переменная запроса представляет собой `IEnumerable`\<string\>.  
  
3.  Итерация переменной запроса выполняется в операторе `foreach` Поскольку переменная запроса является последовательностью строк, переменная итерации также является строкой.  
  
## Запросы, выполняющие преобразование исходных данных  
 На следующем рисунке показана операция запроса [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], выполняющая простое преобразование данных.  В качестве входных данных запрос получает последовательность объектов `Customer` и выбирает в результате только свойство `Name`.  Поскольку `Name` является строкой, запрос создает последовательность строк в качестве выходных данных.  
  
 ![Запрос, преобразующий тип данных](../../../../csharp/programming-guide/concepts/linq/media/linq_flow2.png "LINQ\_flow2")  
  
1.  Аргумент типа источника данных определяет тип переменной диапазона.  
  
2.  Оператор `select` возвращает свойство `Name` вместо целого объекта `Customer`.  Поскольку `Name` является строкой, аргумент типа `custNameQuery` является `string`, а не `Customer`.  
  
3.  Поскольку `custNameQuery` является последовательностью строк, переменная итерации цикла `foreach` также должна быть `string`.  
  
 На следующем рисунке показано немного более сложное преобразование.  Оператор `select` возвращает анонимный тип, захватывающий только два члена исходного объекта `Customer`.  
  
 ![Запрос, преобразующий тип данных](../../../../csharp/programming-guide/concepts/linq/media/linq_flow3.png "LINQ\_flow3")  
  
1.  Аргумент типа источника данных всегда является типом переменной диапазона в запросе.  
  
2.  Так как оператор `select` создает анонимный тип, переменная запроса должна быть неявно типизирована с помощью `var`.  
  
3.  Поскольку тип переменной запроса неявный, переменная итерации в цикле `foreach` также должна быть неявной.  
  
## Разрешение компилятору определять сведения о типе  
 Несмотря на то, что необходимо обладать знаниями об отношениях типов в операции запроса, существует возможность передачи выполнения всех действий компилятору.  Ключевое слово [var](../../../../csharp/language-reference/keywords/var.md) можно использовать для любой локальной переменной в операции запроса.  Следующий рисунок похож на пример 2, рассмотренный выше.  Однако компилятор предоставляет строгий тип для каждой переменной в операции запроса.  
  
 ![Тип потока с неявным вводом](../../../../csharp/programming-guide/concepts/linq/media/linq_flow4.png "LINQ\_flow4")  
  
 Дополнительные сведения о `var` см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## См. также  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)