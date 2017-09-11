---
title: "Дополнительные способы создания запросов (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 028d978e-215b-4d50-ba70-adce0659386d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 91460ed99854edda829503d451728c4274d7ba2b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="advanced-query-techniques-linq-to-xml-c"></a><span data-ttu-id="b5388-102">Дополнительные способы создания запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-102">Advanced Query Techniques (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b5388-103">В этом разделе представлены примеры расширенных методов выполнения запросов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5388-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5388-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="b5388-104">In This Section</span></span>  
  
|<span data-ttu-id="b5388-105">Раздел</span><span class="sxs-lookup"><span data-stu-id="b5388-105">Topic</span></span>|<span data-ttu-id="b5388-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b5388-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b5388-107">Практическое руководство. Объединение двух коллекций (C#) (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-107">How to: Join Two Collections (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="b5388-108">Показывает, как использовать предложение `Join` для реализации преимуществ связей в XML-данных.</span><span class="sxs-lookup"><span data-stu-id="b5388-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="b5388-109">Практическое руководство. Создание иерархии с помощью группировки (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-109">How to: Create Hierarchy Using Grouping (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="b5388-110">Показывает способы группирования данных и последующего формирования XML на основе этого группирования.</span><span class="sxs-lookup"><span data-stu-id="b5388-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="b5388-111">Практическое руководство. Запрос LINQ to XML с использованием XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-111">How to: Query LINQ to XML Using XPath (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="b5388-112">Показывает способы получения коллекций на основе запросов XPath.</span><span class="sxs-lookup"><span data-stu-id="b5388-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="b5388-113">Практическое руководство. Запись метода оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-113">How to: Write a LINQ to XML Axis Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="b5388-114">Показывает способы написания метода оси [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5388-114">Shows how to write a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axis method.</span></span>|  
|[<span data-ttu-id="b5388-115">Практическое руководство. Выполнение потоковых преобразований текста в XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-115">How to: Perform Streaming Transformations of Text to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transformations-of-text-to-xml.md)|<span data-ttu-id="b5388-116">Показывает способы преобразования очень больших текстовых файлов в XML при сохранении небольшой потребности в памяти.</span><span class="sxs-lookup"><span data-stu-id="b5388-116">Shows how to transform very large text files into XML while maintaining a small memory footprint.</span></span>|  
|[<span data-ttu-id="b5388-117">Практическое руководство. Перечисление всех узлов в дереве (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-117">How to: List All Nodes in a Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="b5388-118">Представляет вспомогательный метод, отображающий список всех узлов в XML-дереве.</span><span class="sxs-lookup"><span data-stu-id="b5388-118">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="b5388-119">Он полезен при отладке кода, изменяющего XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="b5388-119">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="b5388-120">Практическое руководство. Извлечение абзацев из документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-120">How to: Retrieve Paragraphs from an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="b5388-121">Представляет код, открывающий документ Office Open XML и получающий абзацы в коллекции объектов XElement objects, текст абзацев и их стиль.</span><span class="sxs-lookup"><span data-stu-id="b5388-121">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="b5388-122">Практическое руководство. Изменение документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-122">How to: Modify an Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="b5388-123">Представляет код, открывающий, изменяющий и сохраняющий документ Office Open XML.</span><span class="sxs-lookup"><span data-stu-id="b5388-123">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="b5388-124">Практическое руководство. Заполнение дерева XML из файловой системы (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-124">How to: Populate an XML Tree from the File System (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="b5388-125">Представляет код, создающий XML-дерево из файловой системы.</span><span class="sxs-lookup"><span data-stu-id="b5388-125">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5388-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b5388-126">See Also</span></span>  
 [<span data-ttu-id="b5388-127">Выполнение запросов к деревьям XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b5388-127">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

