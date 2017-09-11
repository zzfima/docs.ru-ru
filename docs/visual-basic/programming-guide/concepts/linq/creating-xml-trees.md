---
title: "Создание деревьев XML (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: e86ba12b-17de-4579-81bb-66322b84cfbe
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c60746a3da6255e4c245febf55151b41186a75b7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-trees-visual-basic"></a><span data-ttu-id="98cc3-102">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-102">Creating XML Trees (Visual Basic)</span></span>
<span data-ttu-id="98cc3-103">Одна из самых распространенных задач при работе с XML состоит в построении XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="98cc3-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="98cc3-104">В этом разделе описывается несколько способов создания таких деревьев.</span><span class="sxs-lookup"><span data-stu-id="98cc3-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98cc3-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="98cc3-105">In This Section</span></span>  
  
|<span data-ttu-id="98cc3-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="98cc3-106">Topic</span></span>|<span data-ttu-id="98cc3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="98cc3-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="98cc3-108">Функциональное построение (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-108">Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="98cc3-109">Содержит общие сведения о функциональном построении в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="98cc3-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="98cc3-110">Функциональное построение позволяет создавать все XML-дерево или его часть с помощью одной инструкции.</span><span class="sxs-lookup"><span data-stu-id="98cc3-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="98cc3-111">В этом разделе также показано, как внедрять запросы при построении XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="98cc3-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="98cc3-112">Знакомство с литералами XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98cc3-112">Introduction to XML Literals in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)|<span data-ttu-id="98cc3-113">Содержит краткое введение в построение деревьев в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] с помощью XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="98cc3-113">Provides a quick introduction to creating trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using XML literals.</span></span> <span data-ttu-id="98cc3-114">Этот раздел содержит ссылки на документацию [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] по XML-литералам.</span><span class="sxs-lookup"><span data-stu-id="98cc3-114">This topic includes links to the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] documentation of XML literals.</span></span>|  
|[<span data-ttu-id="98cc3-115">Сравнение клонирования и Присоединение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-115">Cloning vs. Attaching (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="98cc3-116">Иллюстрирует различие между добавлением узлов из существующего XML-дерева (узлы клонируются и затем добавляются) и добавлением узлов, не имеющих родителя (такие узлы просто присоединяются).</span><span class="sxs-lookup"><span data-stu-id="98cc3-116">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="98cc3-117">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-117">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="98cc3-118">Показывает, как выполнить синтаксический анализ XML из множества источников.</span><span class="sxs-lookup"><span data-stu-id="98cc3-118">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="98cc3-119">основан на основе <xref:System.Xml.XmlReader>, который используется для синтаксического анализа XML.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="98cc3-119"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="98cc3-120">Практическое руководство: заполнение дерева XML с помощью XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-120">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="98cc3-121">Показано, как заполнять XML-дерево с помощью <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="98cc3-121">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="98cc3-122">Практическое руководство: проверка с использованием XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-122">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="98cc3-123">Показывает, как проверять XML-дерево с помощью XSD.</span><span class="sxs-lookup"><span data-stu-id="98cc3-123">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="98cc3-124">Допустимое содержимое объектов XElement и XDocument</span><span class="sxs-lookup"><span data-stu-id="98cc3-124">Valid Content of XElement and XDocument Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects.md)|<span data-ttu-id="98cc3-125">Описывает допустимые аргументы, которые можно передавать конструкторам, а также методы, которые можно использовать для добавления содержимого в элементы и документы.</span><span class="sxs-lookup"><span data-stu-id="98cc3-125">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98cc3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="98cc3-126">See Also</span></span>  
 [<span data-ttu-id="98cc3-127">Руководство по программированию (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98cc3-127">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
