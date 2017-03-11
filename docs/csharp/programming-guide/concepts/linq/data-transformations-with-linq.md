---
title: "Преобразования данных с помощью LINQ (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], преобразования данных"
  - "исходные элементы [LINQ в C#]"
  - "объединение нескольких вводов [LINQ в C#]"
  - "несколько выводов для одной выходной последовательности [LINQ в C#]"
  - "подмножество исходных элементов [LINQ в C#]"
  - "источники данных [LINQ в C#], преобразования данных"
  - "преобразования данных [LINQ в C#]"
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Преобразования данных с помощью LINQ (C#)
[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] используется не только для извлечения данных.  Это также мощное средство для преобразования данных.  С помощью запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] можно использовать исходную последовательность в качестве входных данных и изменять ее различными способами для создания новой выходной последовательности.  Можно изменить последовательность сама без изменения элементов сами, сортировка и группирование. Однако при необходимости наиболее запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] предусмотрена удобная возможность создания новых типов.  Это выполняется в предложении [select](../../../../csharp/language-reference/keywords/select-clause.md).  Например, можно выполнить следующие задачи.  
  
-   Объединить несколько входных последовательностей в одну выходную последовательность, которая имеет новый тип.  
  
-   Создать выходные последовательности, элементы которых состоят только из одного или нескольких свойств каждого элемента в исходной последовательности.  
  
-   Создать выходные последовательности, элементы которых состоят из результатов операций, выполняемых над исходными данными.  
  
-   Создать выходные последовательности в другом формате.  Например, можно преобразовать данные из строк SQL или текстовых файлов в XML.  
  
 Это только несколько примеров.  Разумеется, эти преобразования могут объединяться различными способами в одном запросе.  Более того, выходные последовательности одного запроса могут использоваться как входные последовательности для нового запроса.  
  
## Соединение нескольких входных последовательностей в одну выходную  
 Запрос [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] можно использовать для создания выходной последовательности, содержащей элементы из нескольких входных последовательностей.  В следующем примере показано объединение двух находящихся в памяти структур данных, но те же принципы могут применяться для соединения данных из источников XML, SQL или DataSet.  Предположим, что существуют два следующих типа классов.  
  
 [!code-cs[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#7)]  
  
 В следующем примере показан запрос.  
  
 [!code-cs[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#8)]  
  
 Дополнительные сведения см. в разделах [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md) и [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## Выбор подмножества каждого исходного элемента  
 Существует два основных способа выбора подмножества каждого элемента в исходной последовательности.  
  
1.  Чтобы выбрать только один член исходного элемента, используйте операцию dot.  В следующем примере предполагается, что объект `Customer` содержит несколько открытых свойств, включая строку с именем `City`.  При выполнении этот запрос создаст выходную последовательность строк.  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  Для создания элементов, содержащих более одного свойства исходного элемента, можно использовать инициализатор объектов либо с именованным объектом, либо с анонимным типом.  В следующем примере показано использование анонимного типа для инкапсуляции двух свойств из каждого элемента `Customer`.  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Дополнительные сведения см. в разделах [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) и [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## Преобразование находящихся в памяти объектов в XML  
 Запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] упрощают преобразования данных между структурами данных в памяти, базами данных SQL, наборами данных [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] и потоками или документами XML.  В следующем примере объекты в находящейся в памяти структуре данных преобразуются в XML\-элементы.  
  
 [!code-cs[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#9)]  
  
 Код формирует следующие выходные XML\-данные.  
  
```  
< Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Дополнительные сведения см. в разделе [Создание XML\-деревьев на языке C\#](../Topic/Creating%20XML%20Trees%20in%20C%23%20\(LINQ%20to%20XML\)1.md).  
  
## Выполнение операций над исходными элементами  
 Выходная последовательность может не содержать какие\-либо элементы или свойства элементов из исходной последовательности.  Результатом может быть последовательность значений, вычисляемых с использованием исходных элементов в качестве входных аргументов.  При выполнении следующего простого запроса выводится последовательность строк, значения которых рассчитаны на основе исходной последовательности элементов типа `double`.  
  
> [!NOTE]
>  Вызов методов в выражениях запроса не поддерживается, если запрос будет перенесен в какой\-либо другой домен.  Например, невозможно вызвать обычный C\# метод в [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)], так как в SQL Server для него отсутствует контекст.  Тем не менее, хранимые процедуры можно сопоставить методам и вызывать последние.  Дополнительные сведения см. в разделе [Хранимые процедуры](../Topic/Stored%20Procedures.md).  
  
 [!code-cs[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#10)]  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)   
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md)   
 [Практическое руководство. Объединение данных с помощью соединений](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)