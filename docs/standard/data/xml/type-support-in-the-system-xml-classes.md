---
title: "Поддержка типов в классах System.Xml"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 14821ef78f20d1ff303afacb42415e4017a92742
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="f280e-102">Поддержка типов в классах System.Xml</span><span class="sxs-lookup"><span data-stu-id="f280e-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="f280e-103">На платформе .NET Framework версии 2.0 основные классы XML были улучшены, чтобы включить возможности поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="f280e-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="f280e-104">Классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> включают функции поддержки типов, включая возможность преобразования между собой типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="f280e-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="f280e-105">На платформе .NET Framework версии 2.0 классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> были улучшены, чтобы включить функции поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="f280e-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
-   <span data-ttu-id="f280e-106"><xref:System.Xml.XmlReader> И <xref:System.Xml.XPath.XPathNavigator> каждого классам относятся **SchemaInfo** свойство, которое возвращает сведения о схеме на узле.</span><span class="sxs-lookup"><span data-stu-id="f280e-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
-   <span data-ttu-id="f280e-107">**ReadContentAs** и **ReadElementContentAs** и методов для <xref:System.Xml.XmlReader> класс считывают текстовое значение и преобразовать его в значение CLR за один вызов метода.</span><span class="sxs-lookup"><span data-stu-id="f280e-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
-   <span data-ttu-id="f280e-108">Метод <xref:System.Xml.XmlWriter.WriteValue%2A> класса <xref:System.Xml.XmlWriter> преобразует тип CLR в тип схемы XML при записи XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f280e-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
-   <span data-ttu-id="f280e-109">**ValueAs** и <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> свойства <xref:System.Xml.XPath.XPathNavigator> класс возвращает значение узла и преобразовать его в значение CLR за один вызов метода.</span><span class="sxs-lookup"><span data-stu-id="f280e-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f280e-110">На платформе .NET Framework версии 1.0 класс <xref:System.Xml.XmlConvert> был нужен для взаимного преобразования типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="f280e-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f280e-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="f280e-111">In This Section</span></span>  
 [<span data-ttu-id="f280e-112">Сопоставление типов данных XML с типами среды CLR</span><span class="sxs-lookup"><span data-stu-id="f280e-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="f280e-113">Описывает сопоставления типов данных XML и типов CLR по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f280e-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="f280e-114">Примечания по реализации поддержки типов XML</span><span class="sxs-lookup"><span data-stu-id="f280e-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="f280e-115">Обсуждаются некоторые детали реализации поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="f280e-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="f280e-116">Преобразование типов данных XML</span><span class="sxs-lookup"><span data-stu-id="f280e-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="f280e-117">Описывает использование класса <xref:System.Xml.XmlConvert> для взаимного преобразования типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="f280e-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f280e-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f280e-118">Related Sections</span></span>  
 [<span data-ttu-id="f280e-119">Доступ к строго типизированным XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="f280e-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
