---
title: "Общие сведения о программировании LINQ to XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2dfa9b6f-5890-461d-b81c-316853c7f320
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4306be3540577bf921eff71dbd9dd822707b33dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-programming-overview-c"></a><span data-ttu-id="03a5e-102">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-102">LINQ to XML Programming Overview (C#)</span></span>
<span data-ttu-id="03a5e-103">В этих подразделах содержится обзор высокого уровня о классах [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], а также подробные сведения о трех наиболее важных классах.</span><span class="sxs-lookup"><span data-stu-id="03a5e-103">These topics provide high-level overview information about the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes, as well as detailed information about three of the most important classes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03a5e-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="03a5e-104">In This Section</span></span>  
  
|<span data-ttu-id="03a5e-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="03a5e-105">Topic</span></span>|<span data-ttu-id="03a5e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="03a5e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="03a5e-107">Сравнение функционального и процедурного программирования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-107">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-vs-procedural-programming-linq-to-xml.md)|<span data-ttu-id="03a5e-108">Содержит представление высокого уровня о двух принципиальных подходах к написанию приложений LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="03a5e-108">Provides a high level view of the two principle approaches to writing LINQ to XML applications.</span></span>|  
|[<span data-ttu-id="03a5e-109">Общие сведения о классах LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-109">LINQ to XML Classes Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-classes-overview.md)|<span data-ttu-id="03a5e-110">Содержит общие сведения о классах [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a5e-110">Provides an overview of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes.</span></span>|  
|[<span data-ttu-id="03a5e-111">Общие сведения о классе XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-111">XElement Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md)|<span data-ttu-id="03a5e-112">Вводит класс <xref:System.Xml.Linq.XElement>, представляющий XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="03a5e-112">Introduces the <xref:System.Xml.Linq.XElement> class, which represents XML elements.</span></span> <span data-ttu-id="03a5e-113">Класс <xref:System.Xml.Linq.XElement> является одним из фундаментальных элементов иерархии классов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03a5e-113"><xref:System.Xml.Linq.XElement> is one of the fundamental classes in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] class hierarchy.</span></span>|  
|[<span data-ttu-id="03a5e-114">Общие сведения о классе XAttribute (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-114">XAttribute Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md)|<span data-ttu-id="03a5e-115">Вводит класс <xref:System.Xml.Linq.XAttribute>, который представляет XML-атрибуты.</span><span class="sxs-lookup"><span data-stu-id="03a5e-115">Introduces the <xref:System.Xml.Linq.XAttribute> class, which represents XML attributes.</span></span>|  
|[<span data-ttu-id="03a5e-116">Общие сведения о классе XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-116">XDocument Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md)|<span data-ttu-id="03a5e-117">Вводит класс <xref:System.Xml.Linq.XDocument>, который представляет XML-документы.</span><span class="sxs-lookup"><span data-stu-id="03a5e-117">Introduces the <xref:System.Xml.Linq.XDocument> class, which represents XML documents.</span></span>|  
|[<span data-ttu-id="03a5e-118">Практическое руководство. Сборка примеров LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-118">How to: Build LINQ to XML Examples (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-build-linq-to-xml-examples.md)|<span data-ttu-id="03a5e-119">Содержит директивы `Using`, необходимые для создания примеров LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="03a5e-119">Contains the `Using` directives that are required to build the LINQ to XML examples.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03a5e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="03a5e-120">See Also</span></span>  
 [<span data-ttu-id="03a5e-121">Руководство по программированию (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="03a5e-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
