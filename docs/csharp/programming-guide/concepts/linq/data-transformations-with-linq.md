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
ms.openlocfilehash: 393e3bd24c4bc8b89064e01e1048b24254f5f83b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635955"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="f11fb-102">Преобразования данных с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="f11fb-102">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="f11fb-103">LINQ используется не только для получения данных.</span><span class="sxs-lookup"><span data-stu-id="f11fb-103">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="f11fb-104">Это эффективный инструмент для их преобразования.</span><span class="sxs-lookup"><span data-stu-id="f11fb-104">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="f11fb-105">С помощью запросов LINQ можно использовать исходную последовательность в качестве входных данных и изменять ее разными способами для создания новой выходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="f11fb-105">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="f11fb-106">Можно изменить саму последовательность, не изменяя элементы, с помощью сортировки и группировки.</span><span class="sxs-lookup"><span data-stu-id="f11fb-106">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="f11fb-107">Но самой интересной функцией запросов LINQ можно назвать возможность создания новых типов.</span><span class="sxs-lookup"><span data-stu-id="f11fb-107">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="f11fb-108">Это выполняется в предложении [select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f11fb-108">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="f11fb-109">Например, можно выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="f11fb-109">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="f11fb-110">Объединение нескольких входных последовательностей в одну выходную последовательность, имеющую новый тип.</span><span class="sxs-lookup"><span data-stu-id="f11fb-110">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="f11fb-111">Создание выходных последовательностей, элементы которых состоят из одного или нескольких свойств каждого элемента в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="f11fb-111">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="f11fb-112">Создание выходных последовательностей, элементы которых состоят из результатов операций, выполняемых с источником данных.</span><span class="sxs-lookup"><span data-stu-id="f11fb-112">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="f11fb-113">Создание выходных последовательностей в другом формате.</span><span class="sxs-lookup"><span data-stu-id="f11fb-113">Create output sequences in a different format.</span></span> <span data-ttu-id="f11fb-114">Например, можно преобразовать данные из строк SQL или текстовых файлов в XML.</span><span class="sxs-lookup"><span data-stu-id="f11fb-114">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="f11fb-115">Это лишь несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="f11fb-115">These are just several examples.</span></span> <span data-ttu-id="f11fb-116">Очевидно, что эти преобразования могут сочетаться различными способами в одном запросе.</span><span class="sxs-lookup"><span data-stu-id="f11fb-116">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="f11fb-117">Более того, выходную последовательность одного запроса можно использовать как входную последовательность для нового запроса.</span><span class="sxs-lookup"><span data-stu-id="f11fb-117">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="f11fb-118">Объединение нескольких входных последовательностей в одну выходную</span><span class="sxs-lookup"><span data-stu-id="f11fb-118">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="f11fb-119">Запрос LINQ можно использовать для создания выходной последовательности, содержащей элементы из нескольких входных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="f11fb-119">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="f11fb-120">Следующий пример демонстрирует объединение двух структур данных в памяти, однако те же принципы могут применяться для объединения данных из источников XML, SQL или DataSet.</span><span class="sxs-lookup"><span data-stu-id="f11fb-120">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="f11fb-121">Рассмотрим следующие два типа классов:</span><span class="sxs-lookup"><span data-stu-id="f11fb-121">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="f11fb-122">В следующем примере показан запрос:</span><span class="sxs-lookup"><span data-stu-id="f11fb-122">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="f11fb-123">Дополнительные сведения см. в разделе [Предложение join](../../../language-reference/keywords/join-clause.md) и [Предложение select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f11fb-123">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="f11fb-124">Выбор подмножества каждого исходного элемента</span><span class="sxs-lookup"><span data-stu-id="f11fb-124">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="f11fb-125">Существует два основных способа выбора подмножества каждого элемента в исходной последовательности:</span><span class="sxs-lookup"><span data-stu-id="f11fb-125">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="f11fb-126">Выбор только одного члена исходного элемента с помощью операции dot.</span><span class="sxs-lookup"><span data-stu-id="f11fb-126">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="f11fb-127">В следующем примере предполагается, что объект `Customer` содержит несколько открытых свойств, включая строку с именем `City`.</span><span class="sxs-lookup"><span data-stu-id="f11fb-127">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="f11fb-128">При выполнении этот запрос создаст выходную последовательность строк.</span><span class="sxs-lookup"><span data-stu-id="f11fb-128">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="f11fb-129">Для создания элементов, содержащих более одного свойства исходного элемента, можно использовать инициализатор объектов с именованным объектом или анонимным типом.</span><span class="sxs-lookup"><span data-stu-id="f11fb-129">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="f11fb-130">В следующем примере показано использование анонимного типа для инкапсуляции двух свойств из каждого элемента `Customer`:</span><span class="sxs-lookup"><span data-stu-id="f11fb-130">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="f11fb-131">Дополнительные сведения см. в разделе [Инициализаторы объектов и коллекций](../../classes-and-structs/object-and-collection-initializers.md) и [Анонимные типы](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="f11fb-131">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="f11fb-132">Преобразование объектов в памяти в XML</span><span class="sxs-lookup"><span data-stu-id="f11fb-132">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="f11fb-133">Запросы LINQ позволяют легко преобразовывать данные между структурами данных в памяти, базами данных SQL, наборами данных ADO.NET и XML-потоками или документами.</span><span class="sxs-lookup"><span data-stu-id="f11fb-133">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="f11fb-134">В следующем примере объекты в структуре данных в памяти преобразуются в XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="f11fb-134">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="f11fb-135">Этот код создает следующий выходные данные XML:</span><span class="sxs-lookup"><span data-stu-id="f11fb-135">The code produces the following XML output:</span></span>  
  
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
  
 <span data-ttu-id="f11fb-136">Дополнительные сведения см. в разделе [Создание деревьев XML C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="f11fb-136">For more information, see [Creating XML Trees in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="f11fb-137">Выполнение операций с исходными элементами</span><span class="sxs-lookup"><span data-stu-id="f11fb-137">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="f11fb-138">Выходная последовательность не может содержать любые элементы или свойства элементов из исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="f11fb-138">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="f11fb-139">Результатом может быть последовательность значений, вычисляемых с использованием исходных элементов в качестве входных аргументов.</span><span class="sxs-lookup"><span data-stu-id="f11fb-139">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span> <span data-ttu-id="f11fb-140">При выполнении следующего простого запроса выводится последовательность строк, значения которых вычисляются на основе исходной последовательности элементов типа `double`.</span><span class="sxs-lookup"><span data-stu-id="f11fb-140">The following simple query, when it is executed, outputs a sequence of strings whose values represent a calculation based on the source sequence of elements of type `double`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f11fb-141">Вызов методов в выражениях запросов не поддерживается, если запрос будет преобразован в некоторую другую область.</span><span class="sxs-lookup"><span data-stu-id="f11fb-141">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="f11fb-142">Например, невозможно вызвать обычный метод C# в [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], так как в SQL Server для него отсутствует контекст.</span><span class="sxs-lookup"><span data-stu-id="f11fb-142">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="f11fb-143">Тем не менее можно сопоставить хранимые процедуры методов и вызвать их.</span><span class="sxs-lookup"><span data-stu-id="f11fb-143">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="f11fb-144">Дополнительные сведения см. в разделе [Хранимые процедуры](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f11fb-144">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="f11fb-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f11fb-145">See also</span></span>

- [<span data-ttu-id="f11fb-146">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="f11fb-146">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="f11fb-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f11fb-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f11fb-148">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f11fb-148">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="f11fb-149">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f11fb-149">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)
- [<span data-ttu-id="f11fb-150">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="f11fb-150">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="f11fb-151">предложение select</span><span class="sxs-lookup"><span data-stu-id="f11fb-151">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
