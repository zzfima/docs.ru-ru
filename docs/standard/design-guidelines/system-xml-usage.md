---
title: Использование System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fb0e1d3dc851f9726905dc375d50cf211dba8400
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149547"
---
# <a name="systemxml-usage"></a><span data-ttu-id="c8c23-102">Использование System.Xml</span><span class="sxs-lookup"><span data-stu-id="c8c23-102">System.Xml Usage</span></span>
<span data-ttu-id="c8c23-103">В этом разделе рассказывается об использовании нескольких типов, которая находится в <xref:System.Xml?displayProperty=nameWithType> пространства имен, который может использоваться для представления XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c8c23-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="c8c23-104">**X DO NOT** использовать <xref:System.Xml.XmlNode> или <xref:System.Xml.XmlDocument> для представления XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c8c23-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="c8c23-105">Предпочтительнее использовать экземпляры <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, или подтипами <xref:System.Xml.Linq.XNode> вместо этого.</span><span class="sxs-lookup"><span data-stu-id="c8c23-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="c8c23-106">`XmlNode` и `XmlDocument` не предназначены для предоставления общедоступных интерфейсов API.</span><span class="sxs-lookup"><span data-stu-id="c8c23-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="c8c23-107">**✓ DO** использовать `XmlReader`, `IXPathNavigable`, или подтип `XNode` как входной или выходной членов, которые принимают или возвращают XML-данные.</span><span class="sxs-lookup"><span data-stu-id="c8c23-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="c8c23-108">Используйте эти абстракции, а не `XmlDocument`, `XmlNode`, или <xref:System.Xml.XPath.XPathDocument>, так как это отделяет методов из конкретных реализаций XML-документа в памяти и позволяет им работать с виртуальной источники XML-данных, которые предоставляют `XNode` , `XmlReader`, или <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="c8c23-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="c8c23-109">**X DO NOT** подкласс `XmlDocument` требуется создать тип, представляющий XML-представление базового источника данных или модели объекта.</span><span class="sxs-lookup"><span data-stu-id="c8c23-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="c8c23-110">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="c8c23-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c8c23-111">*Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c8c23-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c23-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c8c23-112">See also</span></span>

- [<span data-ttu-id="c8c23-113">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="c8c23-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="c8c23-114">Правила использования</span><span class="sxs-lookup"><span data-stu-id="c8c23-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
