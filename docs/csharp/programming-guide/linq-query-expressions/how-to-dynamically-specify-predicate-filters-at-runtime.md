---
title: "Практическое руководство. Динамическое определение фильтров предикатов во время выполнения (Руководство по программированию на C#) | Microsoft Docs"
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
  - "динамические запросы [LINQ в C#]"
  - "фильтры предикатов [C#]"
  - "предикаты [C#]"
  - "запросы [LINQ в C#], фильтры предикатов"
  - "выражения запросов [LINQ в C#], фильтры предикатов"
ms.assetid: 52f2dc7a-8353-4c6e-98d3-eec99a907a5f
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Динамическое определение фильтров предикатов во время выполнения (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В некоторых случаях только во время выполнения удается определить, сколько предикатов нужно применить к исходным элементам в предложении `where`.  Одним из способов динамического определения нескольких фильтров предикатов является использование метода <xref:System.Linq.Enumerable.Contains%2A>, как показано в следующем примере.  Пример состоит из двух частей.  Сначала проект запускается посредством фильтрации по значениям, предоставленным в программе.  Затем проект запускается повторно с использованием входных данных, предоставленных во время выполнения.  
  
### Фильтрация с помощью метода "Contains"  
  
1.  Откройте в Visual Studio новое консольное приложение.  Присвойте ему имя `PredicateFilters`.  
  
2.  Скопируйте класс `StudentClass` из раздела [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) и вставьте его в пространство имен `PredicateFilters`, вложив в класс `Program`.  `StudentClass` предоставляет список объектов `Student`.  
  
3.  Закомментируйте метод `Main` в `StudentClass`.  
  
4.  Замените класс `Program` на следующий код.  
  
     [!code-cs[csProgGuideLINQ#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  Добавьте в метод `Main` в классе `DynamicPredicates` под объявлением `ids` следующую строку.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
6.  Чтобы запустить проект, нажмите клавишу F5.  
  
7.  В окне командной строки выводится следующий результат:  
  
     Garcia: 114  
  
     O'Donnell: 112  
  
     Omelchenko: 111  
  
8.  Следующим этапом является повторный запуск проекта, но с использованием входных данных, введенных во время выполнения, а не массива `ids`.  В **обозревателе решений** щелкните правой кнопкой мыши **PredicateFilters** и выберите пункт **Свойства**.  
  
9. Перейдите на вкладку **Отладка**.  
  
10. В окне **Аргументы командной строки** введите значения 122, 117, 120 и 115, разделяя их пробелами: `122 117 120 115`.  После запуска проекта эти значения становятся элементами параметра `args` метода `Main`.  
  
11. Измените значение `QueryByID(ids)` на `QueryByID(args)` в методе `Main`.  
  
12. Чтобы запустить проект, нажмите клавишу F5.  
  
13. В окне командной строки выводится следующий результат:  
  
     Adams: 120  
  
     Feng: 117  
  
     Garcia: 115  
  
     Tucker: 122  
  
### Фильтрация с использованием оператора "switch"  
  
1.  Оператор `switch` можно использовать для выбора предопределенных альтернативных запросов.  В следующем примере `studentQuery` использует другое предложение `where` в зависимости от того, какой год обучения указан во время выполнения.  
  
2.  Скопируйте следующий метод и вставьте его в класс `DynamicPredicates`.  
  
     [!code-cs[csProgGuideLINQ#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  В окне **Аргументы командной строки** замените идентификационные номера из предыдущей процедуры на целочисленное значение между 1 и 4.  
  
4.  В методе `Main` замените вызов `QueryByID` на следующий вызов, который передает первый элемент массива `args` в качестве аргумента: `QueryByYear(args[0])`.  
  
5.  Чтобы запустить проект, нажмите клавишу F5.  
  
### Использование данного метода в своих приложениях  
  
-   Настраивая данный метод для своего приложения, помните, что для LINQ требуется [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии 3.5 или 4, а проект должен содержать ссылку на библиотеку System.Core.dll и директиву `using` для библиотеки `System.Linq`.  Типы LINQ to SQL, LINQ to XML и LINQ to DataSet требуют дополнительных директив `using` и ссылок.  Дополнительные сведения см. в разделе [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## См. также  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Предложение where](../../../csharp/language-reference/keywords/where-clause.md)