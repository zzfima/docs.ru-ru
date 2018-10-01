---
title: Обработка XML-данных с использованием модели данных XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da8b623d3a73ca8791a0619c67b0ed3bd42447d3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47216257"
---
# <a name="process-xml-data-using-the-xpath-data-model"></a><span data-ttu-id="e6668-102">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="e6668-102">Process XML Data Using the XPath Data Model</span></span>
<span data-ttu-id="e6668-103">Пространство имен <xref:System.Xml?displayProperty=nameWithType> обеспечивает программное представление XML-документов, фрагментов, узлов и наборов узлов в памяти с использованием классов <xref:System.Xml.XmlDocument> и <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="e6668-103">The <xref:System.Xml?displayProperty=nameWithType> namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets in-memory, using the <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> classes.</span></span>  
  
 <span data-ttu-id="e6668-104">Класс <xref:System.Xml.XPath.XPathDocument> обеспечивает быстрое и доступное только для чтения представление XML-документа в памяти с использованием модели данных XPath.</span><span class="sxs-lookup"><span data-stu-id="e6668-104">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="e6668-105">Класс <xref:System.Xml.XmlDocument> обеспечивает изменяемое в памяти представление XML-документа, реализующего модель W3C DOM базового уровня 1 и базового уровня 2.</span><span class="sxs-lookup"><span data-stu-id="e6668-105">The <xref:System.Xml.XmlDocument> class provides an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="e6668-106">Оба класса реализуют интерфейс <xref:System.Xml.XPath.IXPathNavigable> и возвращают объект <xref:System.Xml.XPath.XPathNavigator>, предназначенный для выборки, вычисления, навигации и в некоторых случаях изменения базовых XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e6668-106">Both classes implement the <xref:System.Xml.XPath.IXPathNavigable> interface and return an <xref:System.Xml.XPath.XPathNavigator> object used to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="e6668-107">В следующих разделах описывается функциональность класса <xref:System.Xml.XPath.XPathNavigator>, основанная на возвратившем его классе.</span><span class="sxs-lookup"><span data-stu-id="e6668-107">The following sections describe the functionality of the <xref:System.Xml.XPath.XPathNavigator> class based on the class that returns it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6668-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e6668-108">In This Section</span></span>  
 [<span data-ttu-id="e6668-109">Чтение XML-данных с помощью XPathDocument и XmlDocument</span><span class="sxs-lookup"><span data-stu-id="e6668-109">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 <span data-ttu-id="e6668-110">Описывается, как создать объект класса <xref:System.Xml.XPath.XPathDocument> только для чтения, чтобы считать XML-документ, и как создать редактируемый объект класса <xref:System.Xml.XmlDocument>, чтобы считать и изменить XML-документ.</span><span class="sxs-lookup"><span data-stu-id="e6668-110">Describes how to create a read-only <xref:System.Xml.XPath.XPathDocument> class object to read an XML document and how to create an editable <xref:System.Xml.XmlDocument> class object to read and edit an XML document.</span></span> <span data-ttu-id="e6668-111">В этом разделе также описывается, как возвратить объект <xref:System.Xml.XPath.XPathNavigator> из каждого класса для просмотра и изменения XML-документа.</span><span class="sxs-lookup"><span data-stu-id="e6668-111">This topic also describes how return an <xref:System.Xml.XPath.XPathNavigator> object from each class to navigate and edit an XML document.</span></span>  
  
 [<span data-ttu-id="e6668-112">Выбор, вычисление и отбор XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e6668-112">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="e6668-113">Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для выбора узлов в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument> с помощью запроса XPath, проверки и анализа результатов выражения XPath и определения соответствия узла в XML-документе данному выражению XPath.</span><span class="sxs-lookup"><span data-stu-id="e6668-113">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an XML document matches a given XPath expression.</span></span>  
  
 [<span data-ttu-id="e6668-114">Доступ к XML-данным с помощью класса XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e6668-114">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="e6668-115">Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для перемещения по узлам извлечения XML-данных и доступа к XML-данным со строгой типизацией в объекте <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e6668-115">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to navigate nodes, extract XML data and access strongly typed XML data in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="e6668-116">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e6668-116">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="e6668-117">Описываются методы класса <xref:System.Xml.XPath.XPathNavigator>, используемые для вставки, изменения и удаления узлов и значений из XML-документа, который содержится в объекте <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e6668-117">Describes the methods of the <xref:System.Xml.XPath.XPathNavigator> class used to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span>  
  
 [<span data-ttu-id="e6668-118">Проверка по схеме с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="e6668-118">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="e6668-119">Описываются способы проверки XML-содержимого объекта <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e6668-119">Describes the ways to validate the XML content contained in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6668-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e6668-120">See also</span></span>

- <xref:System.Xml.XmlDocument>  
- <xref:System.Xml.XPath.XPathDocument>  
- <xref:System.Xml.XPath.XPathNavigator>  
- [<span data-ttu-id="e6668-121">Обработка XML-данных с использованием модели DOM</span><span class="sxs-lookup"><span data-stu-id="e6668-121">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)
