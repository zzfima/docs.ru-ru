---
title: "Практическое руководство. Соединение с помощью составных ключей (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "составные ключи [LINQ в C#]"
  - "соединения [C#]"
  - "соединения [C#], составные ключи"
  - "запросы [LINQ в C#], соединения"
  - "выражения запросов [LINQ в C#], соединения"
ms.assetid: 3e015b3f-9cca-4b0c-aa97-dca0d36ea592
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Соединение с помощью составных ключей (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере показано, как выполнить операции соединения, в которых для подстановки нужно использовать более одного ключа.  Для этого применяются составные ключи.  Составной ключ создается как анонимный тип или именованный тип со значениями, которые нужно сравнивать.  Если переменная запроса будет передана за пределы границ метода, используйте именованный тип, переопределяющий <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> для ключа.  Имена свойств и их порядок должны совпадать в каждом ключе.  
  
## Пример  
 В следующем примере демонстрируется использование составного ключа для соединения данных из трех таблиц.  
  
```  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,         d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 Вывод типа в составных ключах зависит от имен свойств в ключах и их порядка.  Если в исходных последовательностях имена свойств не совпадают, в ключах нужно присвоить новые имена.  Например, если в таблицах `Orders` и `OrderDetails` используются разные имена столбцов, можно создать составные ключи, назначив одинаковые имена в анонимных типах:  
  
```  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 Кроме того, составные ключи можно использовать в предложении `group`.  
  
## Компиляция кода  
  
-   Для компиляции и запуска этого кода выполните следующие действия.  
  
-   Откройте документ [Практическое руководство. Подключение к базе данных "Борей"](../Topic/How%20to:%20Connect%20to%20the%20Northwind%20Database.md) и следуйте инструкциям для настройки проекта и создания подключения к базе данных.  Дополнительные сведения см. в разделе [Практическое руководство. Установка образцов баз данных](../Topic/How%20to:%20Install%20Sample%20Databases.md).  
  
-   В файле samples.cs создайте новый пустой метод, принимающий входной параметр Northwind с именем db \(аналогичный другим методам в этом файле\).  Вставьте код из этого примера в текст метода.  
  
-   Измените файл program.cs для вызова нового метода из `Main`.  
  
-   Нажмите клавишу F5, чтобы скомпилировать и выполнить запрос.  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение join](../../../csharp/language-reference/keywords/join-clause.md)   
 [Предложение group](../../../csharp/language-reference/keywords/group-clause.md)