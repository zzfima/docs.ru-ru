---
title: "Статически скомпилированных запросов (LINQ to XML) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ea8e71acf861b93a21296c74254b3ca4d977d0a
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Статически скомпилированных запросов (LINQ to XML) (Visual Basic)
Одним из наиболее важных производительности преимуществ LINQ to XML, в отличие от <xref:System.Xml.XmlDocument>, что в LINQ to XML запросы компилируются статически, тогда как запросы XPath интерпретируются во время выполнения.</xref:System.Xml.XmlDocument> Это встроенная возможность LINQ to XML, поэтому вам не нужно будет принимать какие-либо подготовительные меры для ее использования, однако, чтобы сделать обоснованный выбор той или другой технологии, важно понимать их различие. Данное различие описано в текущем разделе.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Сравнение статически скомпилированных запросов и языка XPath  
 В следующем примере показано, как получать элементы-потомки с указанным именем и атрибут с заданным значением.  
  
 Далее представлено эквивалентное выражение XPath.  
  
```  
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
  
 <xref:System.Linq.Enumerable.Where%2A>Является методом расширения.</xref:System.Linq.Enumerable.Where%2A> Дополнительные сведения см. в разделе [методы расширения](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Поскольку <xref:System.Linq.Enumerable.Where%2A>является методом расширения приведенный выше запрос компилируется так же, как были написаны следующим образом:</xref:System.Linq.Enumerable.Where%2A>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Этот пример приводит к получению в точности таких же результатов, что и два предыдущих примера. Таким образом, демонстрируется возможность эффективной компиляции запросов в вызовы методов со статическими ссылками. В сочетании с семантикой отложенного выполнения итераторов это позволяет повысить производительность. Дополнительные сведения о семантике отложенного выполнения итераторов см. в разделе [отложенное выполнение и отложенное вычисление в LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
>  В этих примерах показаны образцы кода, который может быть составлен компилятором. Действительная реализация может несколько отличаться от этих примеров, однако производительность останется такой же или приблизительно такой же.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Выполнение выражений XPath с помощью XmlDocument  
 В следующем примере используется <xref:System.Xml.XmlDocument>для получения таких же результатов, как показано в предыдущих примерах:</xref:System.Xml.XmlDocument>  
  
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
  
 Этот запрос возвращает такие же выходные данные как примеры использования LINQ to XML. Единственное различие — что LINQ to XML расставляет отступы результирующем файле XML, а <xref:System.Xml.XmlDocument>— нет.</xref:System.Xml.XmlDocument>  
  
 Однако <xref:System.Xml.XmlDocument>подход обычно не выполнить, так и LINQ to XML, поскольку <xref:System.Xml.XmlNode.SelectNodes%2A>метод должен выполнять следующие внутренние при каждом вызове:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument>  
  
-   Анализирует строку, содержащую выражение XPath, и разбивает ее на лексемы.  
  
-   Проверяет лексемы, чтобы подтвердить правильность выражения XPath.  
  
-   Транслирует выражение во внутреннее дерево выражений.  
  
-   Проходит по узлам, выбирает соответствующие узлы на основании оценки выражения и добавляет их в набор результатов.  
  
 При этом выполняется значительно больший объем работы, чем при использовании аналогичного запроса LINQ to XML. Конкретный выигрыш по производительности зависит от различных типов запросов, однако в целом запросы LINQ to XML выполняют меньше работы и поэтому более эффективны, чем операции по оценке выражений XPath с помощью <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument>  
  
## <a name="see-also"></a>См. также  
 [Производительность (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

