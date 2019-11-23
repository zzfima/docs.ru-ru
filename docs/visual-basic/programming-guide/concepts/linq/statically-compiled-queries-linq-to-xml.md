---
title: Статические компилированные запросы (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: e9f56366f1566f831f1e0ea5bd5a06775d698c3d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350580"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Statically Compiled Queries (LINQ to XML) (Visual Basic)

Одним из важнейших преимуществ LINQ to XML перед <xref:System.Xml.XmlDocument> с точки зрения производительности является то, что в LINQ to XML запросы компилируются статически, тогда как запросы XPath интерпретируются во время выполнения. Это встроенная функция LINQ to XML, поэтому вам не нужно будет принимать какие-либо подготовительные меры для ее использования, однако, чтобы сделать обоснованный выбор той или другой технологии, важно понимать их различие. Данное различие описано в текущем разделе.

## <a name="statically-compiled-queries-vs-xpath"></a>Сравнение статически скомпилированных запросов с XPath

В следующем примере показано, как получать элементы-потомки с указанным именем и атрибут с заданным значением.

Далее представлено эквивалентное выражение XPath.

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

Компилятор переписывает выражение запроса из этого примера с использованием синтаксиса запросов, основанных на методах. Код в следующем примере имеет синтаксис запросов, основанных на методах и приводит к получению таких же результатов, что и предыдущий код.

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Метод <xref:System.Linq.Enumerable.Where%2A> является методом расширения. Дополнительные сведения см. в разделе [Методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Поскольку используется метод расширения <xref:System.Linq.Enumerable.Where%2A>, представленный выше запрос компилируется так, как показано далее.

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Этот пример приводит к получению в точности таких же результатов, что и два предыдущих примера. Таким образом, демонстрируется возможность эффективной компиляции запросов в вызовы методов со статическими ссылками. В сочетании с семантикой отложенного выполнения итераторов это позволяет повысить производительность. For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

> [!NOTE]
> В этих примерах показаны образцы кода, который может быть составлен компилятором. Действительная реализация может несколько отличаться от этих примеров, однако производительность останется такой же или приблизительно такой же.

## <a name="executing-xpath-expressions-with-xmldocument"></a>Выполнение выражений XPath с помощью XmlDocument

В следующем примере объект <xref:System.Xml.XmlDocument> используется для получения таких же результатов, что и в предыдущих примерах.

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

Этот запрос возвращает такие же выходные данные, что и в примерах на основе LINQ to XML, за исключением того, что запрос LINQ to XML расставляет отступы в результирующем файле XML, а запрос <xref:System.Xml.XmlDocument> - нет.

Однако производительность подхода на основе <xref:System.Xml.XmlDocument> в целом ниже, чем при использовании LINQ to XML, поскольку метод <xref:System.Xml.XmlNode.SelectNodes%2A> должен при каждом вызове выполнять следующие внутренние операции:

- Анализирует строку, содержащую выражение XPath, и разбивает ее на лексемы.

- Проверяет лексемы, чтобы подтвердить правильность выражения XPath.

- Транслирует выражение во внутреннее дерево выражений.

- Проходит по узлам, выбирает соответствующие узлы на основании оценки выражения и добавляет их в набор результатов.

При этом выполняется значительно больший объем работы, чем при использовании аналогичного запроса LINQ to XML. Конкретный выигрыш по производительности зависит от типа запроса, однако в общем случае запросы LINQ to XML выполняют меньше работы и поэтому более эффективны, чем операции по оценке выражений XPath с помощью <xref:System.Xml.XmlDocument>.

## <a name="see-also"></a>См. также

- [Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
