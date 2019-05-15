---
title: Преобразования данных с помощью LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 5a0c4b0d672e3fd9cfe1528e16070cf1dcbabd69
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64597655"
---
# <a name="data-transformations-with-linq-c"></a>Преобразования данных с помощью LINQ (C#)
[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] предназначен не только для получения данных. Это эффективный инструмент для их преобразования. С помощью запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] можно использовать исходную последовательность в качестве входных данных и изменять ее различными способами для создания новой выходной последовательности. Можно изменить саму последовательность, не изменяя элементы, с помощью сортировки и группировки. Однако самой интересной функцией запросов [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] можно назвать возможность создания новых типов. Это выполняется в предложении [select](../../../../csharp/language-reference/keywords/select-clause.md). Например, можно выполнить следующие задачи.  
  
- Объединение нескольких входных последовательностей в одну выходную последовательность, имеющую новый тип.  
  
- Создание выходных последовательностей, элементы которых состоят из одного или нескольких свойств каждого элемента в исходной последовательности.  
  
- Создание выходных последовательностей, элементы которых состоят из результатов операций, выполняемых с источником данных.  
  
- Создание выходных последовательностей в другом формате. Например, можно преобразовать данные из строк SQL или текстовых файлов в XML.  
  
 Это лишь несколько примеров. Очевидно, что эти преобразования могут сочетаться различными способами в одном запросе. Более того, выходную последовательность одного запроса можно использовать как входную последовательность для нового запроса.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Объединение нескольких входных последовательностей в одну выходную  
 Запрос [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] можно использовать для создания выходной последовательности, содержащей элементы из нескольких входных последовательностей. Следующий пример демонстрирует объединение двух структур данных в памяти, однако те же принципы могут применяться для объединения данных из источников XML, SQL или DataSet. Рассмотрим следующие два типа классов:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 В следующем примере показан запрос:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Дополнительные сведения см. в разделе [Предложение join](../../../../csharp/language-reference/keywords/join-clause.md) и [Предложение select](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Выбор подмножества каждого исходного элемента  
 Существует два основных способа выбора подмножества каждого элемента в исходной последовательности:  
  
1. Выбор только одного члена исходного элемента с помощью операции dot. В следующем примере предполагается, что объект `Customer` содержит несколько открытых свойств, включая строку с именем `City`. При выполнении этот запрос создаст выходную последовательность строк.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Для создания элементов, содержащих более одного свойства исходного элемента, можно использовать инициализатор объектов с именованным объектом или анонимным типом. В следующем примере показано использование анонимного типа для инкапсуляции двух свойств из каждого элемента `Customer`:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) и [Анонимные типы](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Преобразование объектов в памяти в XML  
 Запросы [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] упрощают преобразование данных между структурами данных в памяти, базах данных SQL, наборах данных [!INCLUDE[vstecado](~/includes/vstecado-md.md)] и XML-потоках или XML-документах. В следующем примере объекты в структуре данных в памяти преобразуются в XML-элементы.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Этот код создает следующий выходные данные XML:  
  
```xml  
<Root>  
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
  
 Дополнительные сведения см. в разделе [Создание деревьев XML C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).  
  
## <a name="performing-operations-on-source-elements"></a>Выполнение операций с исходными элементами  
 Выходная последовательность не может содержать любые элементы или свойства элементов из исходной последовательности. Результатом может быть последовательность значений, вычисляемых с использованием исходных элементов в качестве входных аргументов. При выполнении следующего простого запроса выводится последовательность строк, значения которых вычисляются на основе исходной последовательности элементов типа `double`.  
  
> [!NOTE]
>  Вызов методов в выражениях запросов не поддерживается, если запрос будет преобразован в некоторую другую область. Например, невозможно вызвать обычный метод C# в [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], так как в SQL Server для него отсутствует контекст. Тем не менее можно сопоставить хранимые процедуры методов и вызвать их. Дополнительные сведения см. в разделе [Хранимые процедуры](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>См. также

- [LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
- [Выражения запросов LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)
- [предложение select](../../../../csharp/language-reference/keywords/select-clause.md)
