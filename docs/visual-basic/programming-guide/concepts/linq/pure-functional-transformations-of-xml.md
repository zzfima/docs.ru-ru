---
title: "Чисто функциональные преобразования XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce372c12ec2359aa0f3f10e977241cb3d5a71ec8
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="f2f52-102">Чисто функциональные преобразования XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2f52-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="f2f52-103">В этом разделе приведен учебник по функциональным преобразованиям для XML.</span><span class="sxs-lookup"><span data-stu-id="f2f52-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="f2f52-104">В учебнике разъясняются основные принципы и языковые конструкции, которые необходимо понять, чтобы использовать функциональные преобразования. В нем также рассказывается об использовании функциональных преобразований для обработки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f2f52-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="f2f52-105">Несмотря на то что в этом учебнике приведены примеры кода LINQ to XML, все базовые принципы также применяются и к другим технологиям LINQ.</span><span class="sxs-lookup"><span data-stu-id="f2f52-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="f2f52-106">[Учебника: обработка содержимого документа WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) учебник содержит несколько примеров, каждый из которых строится на предыдущий.</span><span class="sxs-lookup"><span data-stu-id="f2f52-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="f2f52-107">Эти примеры демонстрируют подход с использованием чисто функциональных преобразований для обработки XML.</span><span class="sxs-lookup"><span data-stu-id="f2f52-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="f2f52-108">В этом учебнике предполагается знание Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f2f52-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="f2f52-109">В этом учебнике не приводится подробное описание семантики и языковых конструкций, однако в нем есть ссылки на соответствующую документацию по языку.</span><span class="sxs-lookup"><span data-stu-id="f2f52-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="f2f52-110">Требуются также твердые знания базовых принципов программирования и XML, в том числе пространств имен XML.</span><span class="sxs-lookup"><span data-stu-id="f2f52-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2f52-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="f2f52-111">In This Section</span></span>  
  
|<span data-ttu-id="f2f52-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="f2f52-112">Topic</span></span>|<span data-ttu-id="f2f52-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f2f52-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f2f52-114">Введение в чисто функциональные преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2f52-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="f2f52-115">Описывает функциональные преобразования и определяет соответствующую технологию.</span><span class="sxs-lookup"><span data-stu-id="f2f52-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="f2f52-116">Учебник: Отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2f52-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="f2f52-117">Подробно описывает отложенное вычисление и отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="f2f52-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="f2f52-118">Учебное руководство: Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2f52-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="f2f52-119">Учебник, в котором демонстрируется функциональное преобразование.</span><span class="sxs-lookup"><span data-stu-id="f2f52-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2f52-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f52-120">See Also</span></span>  
 [<span data-ttu-id="f2f52-121">Выполнение запросов деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2f52-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
