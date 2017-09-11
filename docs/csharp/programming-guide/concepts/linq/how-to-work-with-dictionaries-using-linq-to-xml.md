---
title: "Практическое руководство. Работа со словарями с помощью LINQ to XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66668c14c472f68dd3da365bd7c7cbc64ccd4365
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="c3ec8-102">Практическое руководство. Работа со словарями с помощью LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c3ec8-102">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>
<span data-ttu-id="c3ec8-103">Часто бывает удобно преобразовать структуры данных в XML, а затем преобразовать XML в другие структуры данных.</span><span class="sxs-lookup"><span data-stu-id="c3ec8-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="c3ec8-104">В этом разделе показана конкретная реализация этого общего подхода на примере преобразования <xref:System.Collections.Generic.Dictionary%602> в XML и обратно.</span><span class="sxs-lookup"><span data-stu-id="c3ec8-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3ec8-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c3ec8-105">Example</span></span>  
 <span data-ttu-id="c3ec8-106">В этом примере используется форма функционального построения, в которой запрос проецирует новые объекты <xref:System.Xml.Linq.XElement>, а итоговая коллекция передается в качестве аргумента конструктору корневого объекта <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="c3ec8-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c3ec8-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="c3ec8-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c3ec8-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c3ec8-108">Example</span></span>  
 <span data-ttu-id="c3ec8-109">Следующий код создает словарь на основе XML.</span><span class="sxs-lookup"><span data-stu-id="c3ec8-109">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="c3ec8-110">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="c3ec8-110">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3ec8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c3ec8-111">See Also</span></span>  
 [<span data-ttu-id="c3ec8-112">Проекции и преобразования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c3ec8-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

