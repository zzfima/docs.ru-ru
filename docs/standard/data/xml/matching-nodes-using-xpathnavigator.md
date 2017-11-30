---
title: "Соответствие узлов с помощью XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a51c358ecb50c94ccde9f86ba80fc8f0670f82d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="b3daf-102">Соответствие узлов с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3daf-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="b3daf-103">Класс <xref:System.Xml.XPath.XPathNavigator> содержит метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> для проверки совпадения узла и выражения XPath.</span><span class="sxs-lookup"><span data-stu-id="b3daf-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="b3daf-104">Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> принимает в качестве входного аргумента выражение XPath и возвращает значение типа <xref:System.Boolean>, указывающее, совпадает ли текущий узел с заданным выражением XPath или скомпилированным объектом <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="b3daf-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="b3daf-105">Совпадение узлов</span><span class="sxs-lookup"><span data-stu-id="b3daf-105">Matching Nodes</span></span>  
 <span data-ttu-id="b3daf-106">Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> возвращает значение `true`, если текущий узел совпадает с заданным выражением XPath.</span><span class="sxs-lookup"><span data-stu-id="b3daf-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="b3daf-107">Например, в следующем примере кода метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> вернет значение `true`, если текущим узлом является элемент `b`, а элемент `b` содержащий атрибут `c`.</span><span class="sxs-lookup"><span data-stu-id="b3daf-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3daf-108">Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> не изменяет состояние объекта <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="b3daf-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3daf-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b3daf-109">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="b3daf-110">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="b3daf-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="b3daf-111">Выберите XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3daf-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="b3daf-112">Вычисление выражения XPath с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b3daf-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="b3daf-113">Типы узлов, распознаваемые запросами XPath</span><span class="sxs-lookup"><span data-stu-id="b3daf-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="b3daf-114">Запросы XPath и пространства имен</span><span class="sxs-lookup"><span data-stu-id="b3daf-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="b3daf-115">Скомпилированные выражения XPath</span><span class="sxs-lookup"><span data-stu-id="b3daf-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
