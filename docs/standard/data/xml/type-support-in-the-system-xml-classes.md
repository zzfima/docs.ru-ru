---
title: Поддержка типов в классах System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
ms.openlocfilehash: cec47d40a0353639bc17b880265f7c15f2f53ac4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710106"
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="a64d0-102">Поддержка типов в классах System.Xml</span><span class="sxs-lookup"><span data-stu-id="a64d0-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="a64d0-103">На платформе .NET Framework версии 2.0 основные классы XML были улучшены, чтобы включить функции поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="a64d0-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="a64d0-104">Классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> включают возможности поддержки типов, включая возможность преобразования между собой типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="a64d0-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="a64d0-105">На платформе .NET Framework версии 2.0 классы <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.XPath.XPathNavigator> были улучшены, чтобы включить функции поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="a64d0-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
- <span data-ttu-id="a64d0-106">Каждый из классов <xref:System.Xml.XmlReader> и <xref:System.Xml.XPath.XPathNavigator> включает свойство **SchemaInfo**, которое возвращает данные о схеме в узле.</span><span class="sxs-lookup"><span data-stu-id="a64d0-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
- <span data-ttu-id="a64d0-107">Методы **ReadContentAs** и **ReadElementContentAs** и методы класса <xref:System.Xml.XmlReader> считывают текстовое значение и преобразуют его в значение CLR за один вызов метода.</span><span class="sxs-lookup"><span data-stu-id="a64d0-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
- <span data-ttu-id="a64d0-108">Метод <xref:System.Xml.XmlWriter.WriteValue%2A> класса <xref:System.Xml.XmlWriter> преобразует тип CLR в тип схемы XML при записи XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a64d0-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
- <span data-ttu-id="a64d0-109">Свойства **ValueAs** и <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> класса <xref:System.Xml.XPath.XPathNavigator> возвращают значение узла и преобразуют его в значение CLR за один вызов метода.</span><span class="sxs-lookup"><span data-stu-id="a64d0-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a64d0-110">На платформе .NET Framework версии 1.0 класс <xref:System.Xml.XmlConvert> был нужен для взаимного преобразования типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="a64d0-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a64d0-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a64d0-111">In This Section</span></span>  
 [<span data-ttu-id="a64d0-112">Сопоставление типов XML-данных с типами CLR</span><span class="sxs-lookup"><span data-stu-id="a64d0-112">Mapping XML Data Types to CLR Types</span></span>](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="a64d0-113">Описывает сопоставления типов данных XML и типов CLR по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a64d0-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="a64d0-114">Примечания по реализации поддержки типов XML</span><span class="sxs-lookup"><span data-stu-id="a64d0-114">XML Type Support Implementation Notes</span></span>](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 <span data-ttu-id="a64d0-115">Обсуждаются некоторые детали реализации поддержки типов.</span><span class="sxs-lookup"><span data-stu-id="a64d0-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="a64d0-116">Преобразование типов XML-данных</span><span class="sxs-lookup"><span data-stu-id="a64d0-116">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 <span data-ttu-id="a64d0-117">Описывает использование класса <xref:System.Xml.XmlConvert> для взаимного преобразования типов схемы XML и типов CLR.</span><span class="sxs-lookup"><span data-stu-id="a64d0-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a64d0-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a64d0-118">Related Sections</span></span>  
 [<span data-ttu-id="a64d0-119">Доступ к XML-данным со строгой типизацией с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="a64d0-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
