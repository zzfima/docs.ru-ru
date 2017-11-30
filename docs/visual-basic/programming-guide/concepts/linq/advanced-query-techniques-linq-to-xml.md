---
title: "Дополнительные способы создания запросов (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79be877c-fadc-4dfb-9f03-426082b13656
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21a12ba1929b0e8fd24ae9e12404691222e397cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="advanced-query-techniques-linq-to-xml-visual-basic"></a><span data-ttu-id="5b753-102">Дополнительные способы создания запросов (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-102">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5b753-103">В этом разделе представлены примеры расширенных методов выполнения запросов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b753-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b753-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="5b753-104">In This Section</span></span>  
  
|<span data-ttu-id="5b753-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="5b753-105">Topic</span></span>|<span data-ttu-id="5b753-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5b753-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5b753-107">Как: объединение двух коллекций (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-107">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="5b753-108">Показывает, как использовать предложение `Join` для реализации преимуществ связей в XML-данных.</span><span class="sxs-lookup"><span data-stu-id="5b753-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="5b753-109">Как: создать иерархию с помощью группирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-109">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="5b753-110">Показывает способы группирования данных и последующего формирования XML на основе этого группирования.</span><span class="sxs-lookup"><span data-stu-id="5b753-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="5b753-111">Как: запрос LINQ to XML с помощью XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-111">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="5b753-112">Показывает способы получения коллекций на основе запросов XPath.</span><span class="sxs-lookup"><span data-stu-id="5b753-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="5b753-113">Как: запись LINQ метод оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-113">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="5b753-114">Показывает способы написания метода оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b753-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="5b753-115">Как: список всех узлов дерева (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-115">How to: List All Nodes in a Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="5b753-116">Представляет вспомогательный метод, отображающий список всех узлов в XML-дереве.</span><span class="sxs-lookup"><span data-stu-id="5b753-116">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="5b753-117">Он полезен при отладке кода, изменяющего XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="5b753-117">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="5b753-118">Как: извлечение абзацев из документа Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-118">How to: Retrieve Paragraphs from an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="5b753-119">Представляет код, открывающий документ Office Open XML и получающий абзацы в коллекции объектов XElement objects, текст абзацев и их стиль.</span><span class="sxs-lookup"><span data-stu-id="5b753-119">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="5b753-120">Как: изменение документа Office Open XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-120">How to: Modify an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="5b753-121">Представляет код, открывающий, изменяющий и сохраняющий документ Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="5b753-121">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="5b753-122">Как: заполнение дерева XML из файловой системы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-122">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="5b753-123">Представляет код, создающий XML-дерево из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="5b753-123">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b753-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5b753-124">See Also</span></span>  
 [<span data-ttu-id="5b753-125">Выполнение запросов деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b753-125">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
