---
title: "Учебник. Управление содержимым в документе WordprocessingML (C#)"
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
ms.assetid: bc9815f8-13d2-4f50-a4d1-b1c0d50d37b3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 293e8de848f83517211e3f3ed640102a2c534764
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-c"></a><span data-ttu-id="0e58d-102">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-102">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>
<span data-ttu-id="0e58d-103">В этом учебнике рассказывается, как применять функциональное преобразование и LINQ to XML для обработки XML-документов.</span><span class="sxs-lookup"><span data-stu-id="0e58d-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="0e58d-104">В примерах на C# запрашивается и обрабатывается информация в документах WordprocessingML в формате Office Open XML, сохраненных программой Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="0e58d-104">The C# examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="0e58d-105">Дополнительные сведения см. на веб-сайте [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573).</span><span class="sxs-lookup"><span data-stu-id="0e58d-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e58d-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="0e58d-106">In This Section</span></span>  
  
|<span data-ttu-id="0e58d-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="0e58d-107">Topic</span></span>|<span data-ttu-id="0e58d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0e58d-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0e58d-109">Форма документов WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-109">Shape of WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="0e58d-110">Приводится краткое описание содержимого документа WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="0e58d-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="0e58d-111">Создание исходного документа в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-111">Creating the Source Office Open XML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="0e58d-112">Приводятся пошаговые указания по созданию исходного документа для запросов, описанных в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="0e58d-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="0e58d-113">Поиск стиля абзаца по умолчанию (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-113">Finding the Default Paragraph Style (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="0e58d-114">Показывает запрос для поиска имени стиля документа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e58d-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="0e58d-115">Извлечение абзацев и стилей (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-115">Retrieving the Paragraphs and Their Styles (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="0e58d-116">Показывает запрос, который применяется для получения коллекции абзацев документа.</span><span class="sxs-lookup"><span data-stu-id="0e58d-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="0e58d-117">Извлечение текста абзацев (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-117">Retrieving the Text of the Paragraphs (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="0e58d-118">В дополнение к предыдущему запросу этот запрос также применяется для получения текста каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="0e58d-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="0e58d-119">Рефакторинг с использованием метода расширения (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-119">Refactoring Using an Extension Method (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="0e58d-120">Упрощает код путем оптимизации кода при помощи метода расширения.</span><span class="sxs-lookup"><span data-stu-id="0e58d-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="0e58d-121">Рефакторинг с использованием чистых функций (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-121">Refactoring Using a Pure Function (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="0e58d-122">Еще более упрощает код путем оптимизации кода при помощи чистой функции.</span><span class="sxs-lookup"><span data-stu-id="0e58d-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="0e58d-123">Проецирование XML в другую форму (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-123">Projecting XML in a Different Shape (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="0e58d-124">Завершает преобразование XML-документа путем проецирования XML-документа в другой форме по сравнению с исходным документом.</span><span class="sxs-lookup"><span data-stu-id="0e58d-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="0e58d-125">Поиск текста в документах Word (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-125">Finding Text in Word Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="0e58d-126">Использует предыдущие запросы, чтобы найти в документе заданную строку текста.</span><span class="sxs-lookup"><span data-stu-id="0e58d-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="0e58d-127">Сведения о документах WordprocessingML в формате Office Open XML (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-127">Details of Office Open XML WordprocessingML Documents (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="0e58d-128">Приводит некоторые подробные сведения о документах Office Open XML WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="0e58d-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e58d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0e58d-129">See Also</span></span>  
 <span data-ttu-id="0e58d-130">[Чистые функциональные преобразования XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="0e58d-130">[Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
 [<span data-ttu-id="0e58d-131">Введение в чистые функциональные преобразования (C#)</span><span class="sxs-lookup"><span data-stu-id="0e58d-131">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)

