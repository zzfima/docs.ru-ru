---
title: "Практическое руководство. Выполнение групповых соединений (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "групповые соединения [LINQ в C#]"
  - "соединения [C#], группа"
  - "запросы [LINQ в C#], соединения"
  - "выражения запросов [LINQ в C#], соединения"
ms.assetid: 31b654c0-77ac-43fa-be11-aa38e14cae2d
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Выполнение групповых соединений (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Групповое соединение можно использовать для создания иерархических структур данных.  Каждый элемент из первой коллекции группируется с набором соответствующих элементов из второй коллекции.  
  
 Например, класс или таблица реляционной базы данных под названием Student может содержать два поля: Id и Name.  Второй класс или таблица реляционной базы данных под названием Course может содержать два поля: StudentId и CourseTitle.  При групповом соединении этих двух источников данных, основанном на сравнении Student.Id и Course.StudentId, приведет к группировке каждого объекта Student с коллекцией объектов Course \(которая может быть пустой\).  
  
> [!NOTE]
>  Каждый элемент первой коллекции отображается в результирующем наборе группового соединения вне зависимости от того, найдены ли соответствующие ему элементы во второй коллекции.  В случае, если такие элементы не найдены, последовательность соответствующих элементов будет пуста.  Селектор результата имеет доступ к каждому элементу первой коллекции.  При этом следует учесть различие с селектором результата в негрупповом соединении: в этом случае селектор не имеет доступа к элементам из первой коллекции, для которых нет совпадений во второй коллекции.  
  
 В первом примере этого раздела показано, как выполнить групповое соединение.  Во втором примере — как использовать групповое соединение для создания элементов XML.  
  
## Пример  
  
### Пример группового соединения  
 В следующем примере выполняется групповое соединение объектов типа `Person` и `Pet` на основе сравнения `Person` свойства `Pet.Owner`.  В отличие от негруппового соединения, в котором создается пара элементов для каждого точного совпадения, групповое соединение создает результирующий объект для каждого элемента первой коллекции, то есть объекта `Person` в данном примере.  Соответствующие элементы из второй коллекции \(в данном примере — объекты `Pet`\) группируются в коллекцию.  Результирующая функция селектора создает для каждого совпадения анонимный тип, состоящий из `Person.FirstName` и коллекции объектов `Pet`.  
  
 [!code-cs[CsLINQProgJoining#5](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_1.cs)]  
  
## Пример  
  
### Применение группового соединения для создания примера XML  
 Групповое соединение позволяет создавать XML с помощью [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Следующий пример аналогичен предыдущему примеру за исключением того, что вместо создания анонимных типов результирующая функция селектора создает элементы XML, представляющие соединенные объекты.  Дополнительные сведения о [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] см. в разделе [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 [!code-cs[CsLINQProgJoining#6](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/how-to-perform-grouped-joins_2.cs)]  
  
## Компиляция кода  
  
-   Создайте в [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)] новый проект **консольного приложения**.  
  
-   Добавьте ссылки на System.Core.dll и System.Xml.Linq.dll, если они отсутствуют.  
  
-   Включите пространства имен <xref:System.Linq> и <xref:System.Xml.Linq>.  
  
-   Скопируйте код из примера в файл program.cs ниже метода `Main`.  Добавьте в метод `Main` строку кода для вызова вставленного метода.  
  
-   Запустите программу.  
  
## См. также  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Join Operations](../../../visual-basic/programming-guide/concepts/linq/join-operations.md)   
 [Практическое руководство. Выполнение внутренних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Практическое руководство. Выполнение левых внешних соединений](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [LINQ to XML](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)