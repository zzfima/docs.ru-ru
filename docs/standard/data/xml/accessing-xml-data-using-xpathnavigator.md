---
title: "Доступ к XML-данным с помощью класса XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c57b46e6-5c77-408f-bc4e-67a5dcc9cc05
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9e0b6d8545fccf9148aaa317b6d936c5c9f02775
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="accessing-xml-data-using-xpathnavigator"></a><span data-ttu-id="7c4c8-102">Доступ к XML-данным с помощью класса XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-102">Accessing XML Data using XPathNavigator</span></span>
<span data-ttu-id="7c4c8-103">Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет методы для перемещения по узлам, извлечения XML-данных, доступа к строго типизированным XML-данным в объектах <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c4c8-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7c4c8-104">In This Section</span></span>  
 [<span data-ttu-id="7c4c8-105">Навигация в наборе узлов с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-105">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="7c4c8-106">Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для перемещения по наборам узлов в объектах <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-106">Describes the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="7c4c8-107">Навигация по узлам атрибутов и пространств имен с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-107">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 <span data-ttu-id="7c4c8-108">Описывает методы класса <xref:System.Xml.XPath.XPathNavigator> для перемещения по наборам узлов атрибутов и пространств имен.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-108">Describes the attribute and namespace node navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="7c4c8-109">Извлечение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-109">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="7c4c8-110">Описывает различные методы извлечения XML-данных из объектов <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-110">Describes the various methods of extracting XML data from an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="7c4c8-111">Доступ к XML-данным со строгой типизацией с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-111">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="7c4c8-112">Описывает методы доступа к строго типизированным XML-данным в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-112">Describes accessing strongly-typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="7c4c8-113">Определяемые пользователем функции и переменные</span><span class="sxs-lookup"><span data-stu-id="7c4c8-113">User Defined Functions and Variables</span></span>](../../../../docs/standard/data/xml/user-defined-functions-and-variables.md)  
 <span data-ttu-id="7c4c8-114">Описывает реализацию пользовательского класса <xref:System.Xml.Xsl.XsltContext> с интерфейсами <xref:System.Xml.Xsl.IXsltContextFunction> и <xref:System.Xml.Xsl.IXsltContextVariable>, которые поддерживают функции и переменные расширения.</span><span class="sxs-lookup"><span data-stu-id="7c4c8-114">Describes implementing a custom <xref:System.Xml.Xsl.XsltContext> class along with the interfaces <xref:System.Xml.Xsl.IXsltContextFunction> and <xref:System.Xml.Xsl.IXsltContextVariable> that support extension functions and variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4c8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7c4c8-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="7c4c8-116">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="7c4c8-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="7c4c8-117">Чтение XML-данных с помощью XPathDocument и XmlDocument</span><span class="sxs-lookup"><span data-stu-id="7c4c8-117">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="7c4c8-118">Выбор, вычисление и отбор XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-118">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="7c4c8-119">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-119">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="7c4c8-120">Проверка по схеме с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7c4c8-120">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
