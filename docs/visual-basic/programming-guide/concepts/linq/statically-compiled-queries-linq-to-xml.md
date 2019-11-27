---
title: Статически скомпилированные запросы (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: e9f56366f1566f831f1e0ea5bd5a06775d698c3d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350580"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="a3d14-102">Статически скомпилированные запросы (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3d14-102">Statically Compiled Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="a3d14-103">Одним из важнейших преимуществ LINQ to XML перед <xref:System.Xml.XmlDocument> с точки зрения производительности является то, что в LINQ to XML запросы компилируются статически, тогда как запросы XPath интерпретируются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a3d14-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="a3d14-104">Это встроенная функция LINQ to XML, поэтому вам не нужно будет принимать какие-либо подготовительные меры для ее использования, однако, чтобы сделать обоснованный выбор той или другой технологии, важно понимать их различие.</span><span class="sxs-lookup"><span data-stu-id="a3d14-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="a3d14-105">Данное различие описано в текущем разделе.</span><span class="sxs-lookup"><span data-stu-id="a3d14-105">This topic explains the difference.</span></span>

## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="a3d14-106">Сравнение статически скомпилированных запросов с XPath</span><span class="sxs-lookup"><span data-stu-id="a3d14-106">Statically Compiled Queries vs. XPath</span></span>

<span data-ttu-id="a3d14-107">В следующем примере показано, как получать элементы-потомки с указанным именем и атрибут с заданным значением.</span><span class="sxs-lookup"><span data-stu-id="a3d14-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>

<span data-ttu-id="a3d14-108">Далее представлено эквивалентное выражение XPath.</span><span class="sxs-lookup"><span data-stu-id="a3d14-108">The following is the equivalent XPath expression:</span></span>

```vb
//Address[@Type='Shipping']
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="a3d14-109">Компилятор переписывает выражение запроса из этого примера с использованием синтаксиса запросов, основанных на методах.</span><span class="sxs-lookup"><span data-stu-id="a3d14-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="a3d14-110">Код в следующем примере имеет синтаксис запросов, основанных на методах и приводит к получению таких же результатов, что и предыдущий код.</span><span class="sxs-lookup"><span data-stu-id="a3d14-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="a3d14-111">Метод <xref:System.Linq.Enumerable.Where%2A> является методом расширения.</span><span class="sxs-lookup"><span data-stu-id="a3d14-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="a3d14-112">Дополнительные сведения см. в статье [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="a3d14-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="a3d14-113">Поскольку используется метод расширения <xref:System.Linq.Enumerable.Where%2A>, представленный выше запрос компилируется так, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="a3d14-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="a3d14-114">Этот пример приводит к получению в точности таких же результатов, что и два предыдущих примера.</span><span class="sxs-lookup"><span data-stu-id="a3d14-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="a3d14-115">Таким образом, демонстрируется возможность эффективной компиляции запросов в вызовы методов со статическими ссылками.</span><span class="sxs-lookup"><span data-stu-id="a3d14-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="a3d14-116">В сочетании с семантикой отложенного выполнения итераторов это позволяет повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="a3d14-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="a3d14-117">Дополнительные сведения о семантике отложенного выполнения итераторов см. [в разделе Отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a3d14-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a3d14-118">В этих примерах показаны образцы кода, который может быть составлен компилятором.</span><span class="sxs-lookup"><span data-stu-id="a3d14-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="a3d14-119">Действительная реализация может несколько отличаться от этих примеров, однако производительность останется такой же или приблизительно такой же.</span><span class="sxs-lookup"><span data-stu-id="a3d14-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>

## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="a3d14-120">Выполнение выражений XPath с помощью XmlDocument</span><span class="sxs-lookup"><span data-stu-id="a3d14-120">Executing XPath Expressions with XmlDocument</span></span>

<span data-ttu-id="a3d14-121">В следующем примере объект <xref:System.Xml.XmlDocument> используется для получения таких же результатов, что и в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="a3d14-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

<span data-ttu-id="a3d14-122">Этот запрос возвращает такие же выходные данные, что и в примерах на основе LINQ to XML, за исключением того, что запрос LINQ to XML расставляет отступы в результирующем файле XML, а запрос <xref:System.Xml.XmlDocument> - нет.</span><span class="sxs-lookup"><span data-stu-id="a3d14-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>

<span data-ttu-id="a3d14-123">Однако производительность подхода на основе <xref:System.Xml.XmlDocument> в целом ниже, чем при использовании LINQ to XML, поскольку метод <xref:System.Xml.XmlNode.SelectNodes%2A> должен при каждом вызове выполнять следующие внутренние операции:</span><span class="sxs-lookup"><span data-stu-id="a3d14-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>

- <span data-ttu-id="a3d14-124">Анализирует строку, содержащую выражение XPath, и разбивает ее на лексемы.</span><span class="sxs-lookup"><span data-stu-id="a3d14-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>

- <span data-ttu-id="a3d14-125">Проверяет лексемы, чтобы подтвердить правильность выражения XPath.</span><span class="sxs-lookup"><span data-stu-id="a3d14-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>

- <span data-ttu-id="a3d14-126">Транслирует выражение во внутреннее дерево выражений.</span><span class="sxs-lookup"><span data-stu-id="a3d14-126">It translates the expression into an internal expression tree.</span></span>

- <span data-ttu-id="a3d14-127">Проходит по узлам, выбирает соответствующие узлы на основании оценки выражения и добавляет их в набор результатов.</span><span class="sxs-lookup"><span data-stu-id="a3d14-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>

<span data-ttu-id="a3d14-128">При этом выполняется значительно больший объем работы, чем при использовании аналогичного запроса LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a3d14-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="a3d14-129">Конкретный выигрыш по производительности зависит от типа запроса, однако в общем случае запросы LINQ to XML выполняют меньше работы и поэтому более эффективны, чем операции по оценке выражений XPath с помощью <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="a3d14-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d14-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a3d14-130">See also</span></span>

- [<span data-ttu-id="a3d14-131">Производительность (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3d14-131">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
