---
title: Обработка XML-данных в памяти
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 317021318153cc87b2eab3db508a9dede9dc05e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569646"
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="e2917-102">Обработка XML-данных в памяти</span><span class="sxs-lookup"><span data-stu-id="e2917-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="e2917-103">Платформа Microsoft .NET Framework включает три модели обработки XML-данных: класс <xref:System.Xml.XmlDocument>, класс <xref:System.Xml.XPath.XPathDocument> и [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="e2917-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="e2917-104">Класс <xref:System.Xml.XmlDocument> реализует базовую модель DOM W3C 1-го уровня и базовые рекомендации объекта DOM 2-го уровня.</span><span class="sxs-lookup"><span data-stu-id="e2917-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="e2917-105">DOM - древовидное представление XML-документа в памяти (кэш).</span><span class="sxs-lookup"><span data-stu-id="e2917-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="e2917-106">С помощью <xref:System.Xml.XmlDocument> и связанных классов можно конструировать XML-документы, загружать данные и обращаться к ним, изменять данные и сохранять изменения.</span><span class="sxs-lookup"><span data-stu-id="e2917-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="e2917-107">Класс <xref:System.Xml.XPath.XPathDocument> - доступное только для чтения хранилище данных в памяти, на базе модели данных XPath.</span><span class="sxs-lookup"><span data-stu-id="e2917-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="e2917-108">В классе <xref:System.Xml.XPath.XPathNavigator> предусмотрено несколько вариантов редактирования и способов навигации с помощью модели курсора для XML-документов в доступном только для чтения классе <xref:System.Xml.XPath.XPathDocument>, а также в классе <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="e2917-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="e2917-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) — это новая модель для обработки XML-данных в платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="e2917-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="e2917-110">Это размещаемая в памяти модель, которая использует синтаксис [LINQ](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="e2917-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="e2917-111">LINQ расширяет синтаксис C# и Visual Basic, обеспечивая новые возможности запросов.</span><span class="sxs-lookup"><span data-stu-id="e2917-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2917-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e2917-112">In This Section</span></span>  
 [<span data-ttu-id="e2917-113">Обработка XML-данных с использованием модели DOM</span><span class="sxs-lookup"><span data-stu-id="e2917-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="e2917-114">Описывает использование класса <xref:System.Xml.XmlDocument> и связанных с ним классов для обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e2917-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="e2917-115">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="e2917-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="e2917-116">Описывает использование классов <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> и <xref:System.Xml.XPath.XPathNavigator> для обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="e2917-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="e2917-117">Обработка XML-данных с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="e2917-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="e2917-118">Содержит краткие общие сведения о LINQ to XML и ссылки на документацию LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="e2917-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e2917-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e2917-119">Related Sections</span></span>  
 [<span data-ttu-id="e2917-120">XML-документы и данные</span><span class="sxs-lookup"><span data-stu-id="e2917-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
