---
title: "Проекции и преобразования (LINQ to XML) (Visual Basic) | Документы Microsoft"
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
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 723685400aadbf883d7ad939e6a1dd5bdeb7ba09
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="c1555-102">Проекции и преобразования (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c1555-103">В этом разделе приводятся примеры [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] проекций и преобразований.</span><span class="sxs-lookup"><span data-stu-id="c1555-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1555-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="c1555-104">In This Section</span></span>  
  
|<span data-ttu-id="c1555-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="c1555-105">Topic</span></span>|<span data-ttu-id="c1555-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c1555-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c1555-107">Практическое руководство: Работа со словарями с использованием LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="c1555-108">Показывает, как преобразовывать словари в формат XML и XML-файлы в формат словарей.</span><span class="sxs-lookup"><span data-stu-id="c1555-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="c1555-109">Практическое руководство: преобразование формы дерева XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="c1555-110">Показывает, как преобразовывать форму XML-документа.</span><span class="sxs-lookup"><span data-stu-id="c1555-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="c1555-111">Практическое руководство: управление типом проекции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="c1555-112">Показывает, как управлять типом запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1555-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="c1555-113">Практическое руководство: создать проекцию нового типа (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="c1555-114">Показывает, как проецировать коллекцию определяемого пользователем типа из запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1555-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="c1555-115">Практическое руководство: проекцию графа объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-115">How to: Project an Object Graph (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="c1555-116">Показывает, как проецировать более сложный граф объекта из запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1555-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="c1555-117">Практическое руководство: проецирование анонимного типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="c1555-118">Показывает, как проецировать коллекцию анонимных объектов из запроса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1555-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="c1555-119">Практическое руководство: Создание текстовых файлов из XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="c1555-120">Показывает, как преобразовывать XML-файл в текстовый файл формата, отличного от XML.</span><span class="sxs-lookup"><span data-stu-id="c1555-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="c1555-121">Практическое руководство: Создание XML из CSV-файлов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="c1555-122">Показывает, как с помощью [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] анализировать файлы CSV и создавать из них XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="c1555-122">Shows how to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1555-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c1555-123">See Also</span></span>  
 [<span data-ttu-id="c1555-124">Выполнение запросов деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1555-124">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
