---
title: Запросы XPath и пространства имен
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: 91503ce0bffa1a9390432a51bff1ef10d80f563a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709781"
---
# <a name="xpath-queries-and-namespaces"></a><span data-ttu-id="d0aa3-102">Запросы XPath и пространства имен</span><span class="sxs-lookup"><span data-stu-id="d0aa3-102">XPath Queries and Namespaces</span></span>
<span data-ttu-id="d0aa3-103">Запросы XPath учитывают наличие пространств имен в XML-документе и могут использовать префиксы пространств имен для дополнения имен элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-103">XPath queries are aware of namespaces in an XML document and can use namespace prefixes to qualify element and attribute names.</span></span> <span data-ttu-id="d0aa3-104">Добавление префикса пространства имен к именам элементов и атрибутов ограничивает набор узлов, возвращаемых запросом XPath, лишь теми узлами, которые принадлежат к определенному пространству имен.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-104">Qualifying element and attribute names with a namespace prefix limits the nodes returned by an XPath query to only those nodes that belong to a specific namespace.</span></span>  
  
 <span data-ttu-id="d0aa3-105">Например, если префикс `books` соответствует пространству имен `http://www.contoso.com/books`, то следующий запрос XPath `/books:books/books:book` выберет только элементы `book` в пространстве имен `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-105">For example if the prefix `books` maps to the namespace `http://www.contoso.com/books`, then the following XPath query `/books:books/books:book` selects only those `book` elements in the namespace `http://www.contoso.com/books`.</span></span>  
  
## <a name="the-xmlnamespacemanager"></a><span data-ttu-id="d0aa3-106">Класс XmlNamespaceManager</span><span class="sxs-lookup"><span data-stu-id="d0aa3-106">The XmlNamespaceManager</span></span>  
 <span data-ttu-id="d0aa3-107">Чтобы использовать пространства имен в запросе XPath, объект, производный от интерфейса <xref:System.Xml.IXmlNamespaceResolver>, например класс <xref:System.Xml.XmlNamespaceManager>, конструируется с URI-кодом пространства имен и префиксом, включаемым в запрос XPath.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-107">To use namespaces in an XPath query, an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface like the <xref:System.Xml.XmlNamespaceManager> class is constructed with the namespace URI and prefix to include in the XPath query.</span></span>  
  
 <span data-ttu-id="d0aa3-108">Объект <xref:System.Xml.XmlNamespaceManager> можно использовать в запросе любым из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-108">The <xref:System.Xml.XmlNamespaceManager> object may be used in the query in each of the following ways.</span></span>  
  
- <span data-ttu-id="d0aa3-109">Объект <xref:System.Xml.XmlNamespaceManager> связывается с существующим объектом <xref:System.Xml.XPath.XPathExpression> с помощью метода <xref:System.Xml.XPath.XPathExpression.SetContext%2A> объекта <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-109">The <xref:System.Xml.XmlNamespaceManager> object is associated with an existing <xref:System.Xml.XPath.XPathExpression> object by using the <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method of the <xref:System.Xml.XPath.XPathExpression> object.</span></span> <span data-ttu-id="d0aa3-110">Также можно скомпилировать новый объект <xref:System.Xml.XPath.XPathExpression> с помощью статического метода <xref:System.Xml.XPath.XPathExpression.Compile%2A>, который принимает в качестве параметров строку, представляющую выражение XPath, и объект <xref:System.Xml.XmlNamespaceManager>, а затем возвращает новый объект <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-110">You may also compile a new <xref:System.Xml.XPath.XPathExpression> object using the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method which takes a string representing the XPath expression and an <xref:System.Xml.XmlNamespaceManager> object as parameters and returns a new <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
- <span data-ttu-id="d0aa3-111">Сам объект <xref:System.Xml.XmlNamespaceManager> передается в качестве параметра методу класса <xref:System.Xml.XPath.XPathNavigator> вместе со строкой, представляющей выражение XPath.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-111">The <xref:System.Xml.XmlNamespaceManager> object itself is passed as a parameter to an accepting <xref:System.Xml.XPath.XPathNavigator> class method along with a string representing the XPath expression.</span></span>  
  
 <span data-ttu-id="d0aa3-112">Далее представлены методы класса <xref:System.Xml.XPath.XPathNavigator>, которые принимают в качестве параметра объект, производный от интерфейса <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-112">The following are the methods of the <xref:System.Xml.XPath.XPathNavigator> class that accept an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface as a parameter.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a><span data-ttu-id="d0aa3-113">Пространство имен по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d0aa3-113">The Default Namespace</span></span>  
 <span data-ttu-id="d0aa3-114">В следующем XML-документе используется пространство имен по умолчанию с пустым префиксом, чтобы объявить пространство имен `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-114">In the XML document that follows, the default namespace with an empty prefix is used to declare the `http://www.contoso.com/books` namespace.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="d0aa3-115">XPath обрабатывает пустой префикс как пространство имен `null`.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-115">XPath treats the empty prefix as the `null` namespace.</span></span> <span data-ttu-id="d0aa3-116">Другими словами, в запросах XPath можно использовать только префиксы, сопоставленные с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-116">In other words, only prefixes mapped to namespaces can be used in XPath queries.</span></span> <span data-ttu-id="d0aa3-117">Это значит, что если нужно построить запрос к пространству имен в XML-документе, то даже если оно является пространством имен по умолчанию, для него необходимо определить префикс.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-117">This means that if you want to query against a namespace in an XML document, even if it is the default namespace, you need to define a prefix for it.</span></span>  
  
 <span data-ttu-id="d0aa3-118">Например, если не определить префикс для представленного выше XML-документа, запрос XPath `/books/book` не вернет никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-118">For example, without defining a prefix for the XML document above, the XPath query `/books/book` would not return any results.</span></span>  
  
 <span data-ttu-id="d0aa3-119">Префикс должен быть привязан, чтобы исключить неоднозначность во время запроса документов, часть узлов которых лежит вне пространства имен, а часть - в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-119">A prefix must be bound to prevent ambiguity when querying documents with some nodes not in a namespace, and some in a default namespace.</span></span>  
  
 <span data-ttu-id="d0aa3-120">В следующем коде определяется префикс для пространства имен по умолчанию и выбираются все элементы `book` из пространства имен `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="d0aa3-120">The following code defines a prefix for the default namespace and selects all the `book` elements from the `http://www.contoso.com/books` namespace.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0aa3-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0aa3-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="d0aa3-122">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="d0aa3-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="d0aa3-123">Выборка XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d0aa3-123">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="d0aa3-124">Вычисление выражения XPath с помощью класса XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d0aa3-124">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="d0aa3-125">Соответствие узлов с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d0aa3-125">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="d0aa3-126">Типы узлов, распознаваемые запросами XPath</span><span class="sxs-lookup"><span data-stu-id="d0aa3-126">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="d0aa3-127">Скомпилированные выражения XPath</span><span class="sxs-lookup"><span data-stu-id="d0aa3-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
