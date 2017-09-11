---
title: "Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic) | Документы Microsoft"
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
ms.assetid: f8028ba8-2dd1-4425-930c-8cc23176ebbc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 28ab2d19cba0344868061fbe1f59c546a569fbdc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="tutorial-manipulating-content-in-a-wordprocessingml-document-visual-basic"></a><span data-ttu-id="950f5-102">Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-102">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>
<span data-ttu-id="950f5-103">В этом учебнике рассказывается, как применять функциональное преобразование и LINQ to XML для обработки XML-документов.</span><span class="sxs-lookup"><span data-stu-id="950f5-103">This tutorial shows how to apply the functional transformational approach and LINQ to XML to manipulate XML documents.</span></span> <span data-ttu-id="950f5-104">Примеры Visual Basic запрашивается и обрабатывается информация в документах Office Open XML WordprocessingML, сохраненных программой Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="950f5-104">The Visual Basic examples query and manipulate information in Office Open XML WordprocessingML documents that are saved by Microsoft Word.</span></span>  
  
 <span data-ttu-id="950f5-105">Дополнительные сведения см. в разделе [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="950f5-105">For more information, see the [OpenXML Developer](http://go.microsoft.com/fwlink/?LinkID=95573) Web site.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="950f5-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="950f5-106">In This Section</span></span>  
  
|<span data-ttu-id="950f5-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="950f5-107">Topic</span></span>|<span data-ttu-id="950f5-108">Описание</span><span class="sxs-lookup"><span data-stu-id="950f5-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="950f5-109">Форма документов WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-109">Shape of WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/shape-of-wordprocessingml-documents.md)|<span data-ttu-id="950f5-110">Приводится краткое описание содержимого документа WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="950f5-110">Provides a quick explanation of details of a WordprocessingML document.</span></span>|  
|[<span data-ttu-id="950f5-111">Создание исходного документа Open XML Office (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-111">Creating the Source Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md)|<span data-ttu-id="950f5-112">Приводятся пошаговые указания по созданию исходного документа для запросов, описанных в этом учебнике.</span><span class="sxs-lookup"><span data-stu-id="950f5-112">Provides step-by-step instructions to create the source document for queries in this tutorial.</span></span>|  
|[<span data-ttu-id="950f5-113">Поиск стиля абзаца по умолчанию (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-113">Finding the Default Paragraph Style (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-the-default-paragraph-style.md)|<span data-ttu-id="950f5-114">Показывает запрос для поиска имени стиля документа по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="950f5-114">Shows a query to find the name of the default style for a document.</span></span>|  
|[<span data-ttu-id="950f5-115">Извлечение абзацев и стилей (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-115">Retrieving the Paragraphs and Their Styles (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-paragraphs-and-their-styles.md)|<span data-ttu-id="950f5-116">Показывает запрос, который применяется для получения коллекции абзацев документа.</span><span class="sxs-lookup"><span data-stu-id="950f5-116">Shows a query that retrieves a collection of the paragraphs of a document.</span></span>|  
|[<span data-ttu-id="950f5-117">Извлечение текста абзацев (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-117">Retrieving the Text of the Paragraphs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/retrieving-the-text-of-the-paragraphs.md)|<span data-ttu-id="950f5-118">В дополнение к предыдущему запросу этот запрос также применяется для получения текста каждого абзаца.</span><span class="sxs-lookup"><span data-stu-id="950f5-118">Augments the previous query to retrieve the text of each paragraph.</span></span>|  
|[<span data-ttu-id="950f5-119">Оптимизация кода с помощью метода расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-119">Refactoring Using an Extension Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-an-extension-method.md)|<span data-ttu-id="950f5-120">Упрощает код путем оптимизации кода при помощи метода расширения.</span><span class="sxs-lookup"><span data-stu-id="950f5-120">Simplifies the code by refactoring using an extension method.</span></span>|  
|[<span data-ttu-id="950f5-121">Оптимизация кода с использованием чистой функции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-121">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)|<span data-ttu-id="950f5-122">Еще более упрощает код путем оптимизации кода при помощи чистой функции.</span><span class="sxs-lookup"><span data-stu-id="950f5-122">Further simplifies the code by refactoring using a pure function.</span></span>|  
|[<span data-ttu-id="950f5-123">Проецирование XML в другую форму (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-123">Projecting XML in a Different Shape (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projecting-xml-in-a-different-shape.md)|<span data-ttu-id="950f5-124">Завершает преобразование XML-документа путем проецирования XML-документа в другой форме по сравнению с исходным документом.</span><span class="sxs-lookup"><span data-stu-id="950f5-124">Completes an XML transformation by projecting XML in a different shape than the original document.</span></span>|  
|[<span data-ttu-id="950f5-125">Поиск текста в документах Word (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-125">Finding Text in Word Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/finding-text-in-word-documents.md)|<span data-ttu-id="950f5-126">Использует предыдущие запросы, чтобы найти в документе заданную строку текста.</span><span class="sxs-lookup"><span data-stu-id="950f5-126">Uses the previous queries to find a specified text string in a document.</span></span>|  
|[<span data-ttu-id="950f5-127">Сведения о Office Open XML-документы WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="950f5-127">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)|<span data-ttu-id="950f5-128">Приводит некоторые подробные сведения о документах Office Open XML WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="950f5-128">Provides some details of Office Open XML WordprocessingML documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="950f5-129">См. также</span><span class="sxs-lookup"><span data-stu-id="950f5-129">See Also</span></span>  
 <span data-ttu-id="950f5-130">[Чисто функциональные преобразования XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="950f5-130">[Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md) </span></span>  
<span data-ttu-id="950f5-131"> [Введение в чисто функциональные преобразования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span><span class="sxs-lookup"><span data-stu-id="950f5-131"> [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)</span></span>
