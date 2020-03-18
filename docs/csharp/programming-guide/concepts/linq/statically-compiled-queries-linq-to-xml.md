---
title: Статически скомпилированные запросы (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 98725cece1006ba13afb64bb8ae17ae6e62c53cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253033"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a>Статически скомпилированные запросы (LINQ to XML) (C#)
Одним из важнейших преимуществ LINQ to XML перед <xref:System.Xml.XmlDocument> с точки зрения производительности является то, что в LINQ to XML запросы компилируются статически, тогда как запросы XPath интерпретируются во время выполнения. Это встроенная возможность LINQ to XML, поэтому вам не нужно будет принимать какие-либо подготовительные меры для ее использования, однако, чтобы сделать обоснованный выбор той или другой технологии, важно понимать их различие. Данное различие описано в текущем разделе.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Сравнение статически скомпилированных запросов с XPath  
 В следующем примере показано, как получать элементы-потомки с указанным именем и атрибут с заданным значением.  
  
 Далее представлено эквивалентное выражение XPath: `//Address[@Type='Shipping']`
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Компилятор переписывает выражение запроса из этого примера с использованием синтаксиса запросов, основанных на методах. Код в следующем примере имеет синтаксис запросов, основанных на методах и приводит к получению таких же результатов, что и предыдущий код.  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Метод <xref:System.Linq.Enumerable.Where%2A> является методом расширения. Дополнительные сведения см. в статье [Методы расширения](../../classes-and-structs/extension-methods.md). Поскольку используется метод расширения <xref:System.Linq.Enumerable.Where%2A>, представленный выше запрос компилируется так, как показано далее.  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Этот пример приводит к получению в точности таких же результатов, что и два предыдущих примера. Таким образом, демонстрируется возможность эффективной компиляции запросов в вызовы методов со статическими ссылками. В сочетании с семантикой отложенного выполнения итераторов это позволяет повысить производительность. Дополнительные сведения о семантике отложенного выполнения итераторов см. в разделе [Отложенное выполнение и отложенное вычисление в LINQ to XML (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
> В этих примерах показаны образцы кода, который может быть составлен компилятором. Действительная реализация может несколько отличаться от этих примеров, однако производительность останется такой же или приблизительно такой же.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Выполнение выражений XPath с помощью XmlDocument  
 В следующем примере объект <xref:System.Xml.XmlDocument> используется для получения таких же результатов, что и в предыдущих примерах.  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 Этот запрос возвращает такие же выходные данные, что и в примерах на основе LINQ to XML, за исключением того, что запрос LINQ to XML расставляет отступы в результирующем файле XML, а запрос <xref:System.Xml.XmlDocument> - нет.  
  
 Однако производительность подхода на основе <xref:System.Xml.XmlDocument> в целом ниже, чем при использовании LINQ to XML, поскольку метод <xref:System.Xml.XmlNode.SelectNodes%2A> должен при каждом вызове выполнять следующие внутренние операции:  
  
- Анализирует строку, содержащую выражение XPath, и разбивает ее на лексемы.  
  
- Проверяет лексемы, чтобы подтвердить правильность выражения XPath.  
  
- Транслирует выражение во внутреннее дерево выражений.  
  
- Проходит по узлам, выбирает соответствующие узлы на основании оценки выражения и добавляет их в набор результатов.  
  
 При этом выполняется значительно больший объем работы, чем при использовании аналогичного запроса LINQ to XML. Конкретный выигрыш по производительности зависит от типа запроса, однако в общем случае запросы LINQ to XML выполняют меньше работы и поэтому более эффективны, чем операции по оценке выражений XPath с помощью <xref:System.Xml.XmlDocument>.  
