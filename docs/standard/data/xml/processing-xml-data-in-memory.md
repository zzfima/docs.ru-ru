---
title: Обработка XML-данных в памяти
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e6e89cafeb4cc580edb9630ba7415a669ea750c
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904411"
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="82f5d-102">Обработка XML-данных в памяти</span><span class="sxs-lookup"><span data-stu-id="82f5d-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="82f5d-103">Платформа Microsoft .NET Framework включает три модели обработки XML-данных: класс <xref:System.Xml.XmlDocument>, класс <xref:System.Xml.XPath.XPathDocument> и [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="82f5d-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="82f5d-104">Класс <xref:System.Xml.XmlDocument> реализует базовую модель DOM W3C 1-го уровня и базовые рекомендации объекта DOM 2-го уровня.</span><span class="sxs-lookup"><span data-stu-id="82f5d-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="82f5d-105">DOM - древовидное представление XML-документа в памяти (кэш).</span><span class="sxs-lookup"><span data-stu-id="82f5d-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="82f5d-106">С помощью <xref:System.Xml.XmlDocument> и связанных классов можно конструировать XML-документы, загружать данные и обращаться к ним, изменять данные и сохранять изменения.</span><span class="sxs-lookup"><span data-stu-id="82f5d-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="82f5d-107">Класс <xref:System.Xml.XPath.XPathDocument> - доступное только для чтения хранилище данных в памяти, на базе модели данных XPath.</span><span class="sxs-lookup"><span data-stu-id="82f5d-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="82f5d-108">В классе <xref:System.Xml.XPath.XPathNavigator> предусмотрено несколько вариантов редактирования и способов навигации с помощью модели курсора для XML-документов в доступном только для чтения классе <xref:System.Xml.XPath.XPathDocument>, а также в классе <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="82f5d-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="82f5d-109">[LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) — это модель для обработки XML-данных, представленная на платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="82f5d-109">[LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) is a model introduced in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="82f5d-110">Это размещаемая в памяти модель, которая использует синтаксис [LINQ](../../../csharp/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="82f5d-110">It's an in-memory model that leverages [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).</span></span> <span data-ttu-id="82f5d-111">LINQ расширяет синтаксис C# и Visual Basic, обеспечивая новые возможности запросов.</span><span class="sxs-lookup"><span data-stu-id="82f5d-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82f5d-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="82f5d-112">In This Section</span></span>  
 [<span data-ttu-id="82f5d-113">Обработка XML-данных с использованием модели DOM</span><span class="sxs-lookup"><span data-stu-id="82f5d-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="82f5d-114">Описывает использование класса <xref:System.Xml.XmlDocument> и связанных с ним классов для обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="82f5d-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="82f5d-115">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="82f5d-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="82f5d-116">Описывает использование классов <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> и <xref:System.Xml.XPath.XPathNavigator> для обработки XML-данных.</span><span class="sxs-lookup"><span data-stu-id="82f5d-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="82f5d-117">Обработка XML-данных с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="82f5d-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="82f5d-118">Содержит краткие общие сведения о LINQ to XML и ссылки на документацию LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="82f5d-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="82f5d-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="82f5d-119">Related Sections</span></span>  
 [<span data-ttu-id="82f5d-120">XML-документы и данные</span><span class="sxs-lookup"><span data-stu-id="82f5d-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
