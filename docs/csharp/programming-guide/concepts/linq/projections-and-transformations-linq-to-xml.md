---
title: "Проекции и преобразования (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bb0457ab-1823-47e6-9d2d-c93c958cc913
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81172ebb440bc2737bbe3f1de0f1dd3cf6e086c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="projections-and-transformations-linq-to-xml-c"></a><span data-ttu-id="93bdd-102">Проекции и преобразования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-102">Projections and Transformations (LINQ to XML) (C#)</span></span>
<span data-ttu-id="93bdd-103">В этом разделе приводятся примеры проекций и преобразований [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bdd-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93bdd-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="93bdd-104">In This Section</span></span>  
  
|<span data-ttu-id="93bdd-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="93bdd-105">Topic</span></span>|<span data-ttu-id="93bdd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="93bdd-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="93bdd-107">Практическое руководство. Работа со словарями с помощью LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-107">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="93bdd-108">Показывает, как преобразовывать словари в формат XML и XML-файлы в формат словарей.</span><span class="sxs-lookup"><span data-stu-id="93bdd-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="93bdd-109">Практическое руководство. Преобразование формы дерева XML (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-109">How to: Transform the Shape of an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="93bdd-110">Показывает, как преобразовывать форму XML-документа.</span><span class="sxs-lookup"><span data-stu-id="93bdd-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="93bdd-111">Практическое руководство. Управление типом проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-111">How to: Control the Type of a Projection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="93bdd-112">Показывает, как управлять типом запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bdd-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="93bdd-113">Практическое руководство. Проецирование нового типа (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-113">How to: Project a New Type (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="93bdd-114">Показывает, как проецировать коллекцию определяемого пользователем типа из запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bdd-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="93bdd-115">Практическое руководство. Проецирование графа объекта (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-115">How to: Project an Object Graph (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="93bdd-116">Показывает, как проецировать более сложный граф объекта из запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bdd-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="93bdd-117">Практическое руководство. Проецирование анонимного типа (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-117">How to: Project an Anonymous Type (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="93bdd-118">Показывает, как проецировать коллекцию анонимных объектов из запроса [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bdd-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="93bdd-119">Практическое руководство. Создание текстовых файлов из XML (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-119">How to: Generate Text Files from XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="93bdd-120">Показывает, как преобразовывать XML-файл в текстовый файл формата, отличного от XML.</span><span class="sxs-lookup"><span data-stu-id="93bdd-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="93bdd-121">Практическое руководство. Создание XML из CSV-файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-121">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="93bdd-122">Показывает, как с помощью [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] анализировать файлы CSV и создавать из них XML-файлы.</span><span class="sxs-lookup"><span data-stu-id="93bdd-122">Shows how to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93bdd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="93bdd-123">See Also</span></span>  
 [<span data-ttu-id="93bdd-124">Выполнение запросов к деревьям XML (C#)</span><span class="sxs-lookup"><span data-stu-id="93bdd-124">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
