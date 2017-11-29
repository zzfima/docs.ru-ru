---
title: "Чисто функциональные преобразования XML-кода (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01ad228d91037de1585d1e66292fddb80c785ada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="23e0c-102">Чисто функциональные преобразования XML-кода (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e0c-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="23e0c-103">В этом разделе приведен учебник по функциональным преобразованиям для XML.</span><span class="sxs-lookup"><span data-stu-id="23e0c-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="23e0c-104">В учебнике разъясняются основные принципы и языковые конструкции, которые необходимо понять, чтобы использовать функциональные преобразования. В нем также рассказывается об использовании функциональных преобразований для обработки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="23e0c-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="23e0c-105">Несмотря на то что в этом учебнике приведены примеры кода LINQ to XML, все базовые принципы также применяются и к другим технологиям LINQ.</span><span class="sxs-lookup"><span data-stu-id="23e0c-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="23e0c-106">[Учебника: обработка содержимого документа WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) учебник содержит несколько примеров, каждый из которых строится на предыдущий.</span><span class="sxs-lookup"><span data-stu-id="23e0c-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="23e0c-107">Эти примеры демонстрируют подход с использованием чисто функциональных преобразований для обработки XML.</span><span class="sxs-lookup"><span data-stu-id="23e0c-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="23e0c-108">Этот учебник предполагает опыт работы с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="23e0c-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="23e0c-109">В этом учебнике не приводится подробное описание семантики и языковых конструкций, однако в нем есть ссылки на соответствующую документацию по языку.</span><span class="sxs-lookup"><span data-stu-id="23e0c-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="23e0c-110">Требуются также твердые знания базовых принципов программирования и XML, в том числе пространств имен XML.</span><span class="sxs-lookup"><span data-stu-id="23e0c-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23e0c-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="23e0c-111">In This Section</span></span>  
  
|<span data-ttu-id="23e0c-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="23e0c-112">Topic</span></span>|<span data-ttu-id="23e0c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="23e0c-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="23e0c-114">Введение в чистые функциональные преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e0c-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="23e0c-115">Описывает функциональные преобразования и определяет соответствующую технологию.</span><span class="sxs-lookup"><span data-stu-id="23e0c-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="23e0c-116">Учебник: Отложенного выполнения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e0c-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)|<span data-ttu-id="23e0c-117">Подробно описывает отложенное вычисление и отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="23e0c-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="23e0c-118">Учебник: Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e0c-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="23e0c-119">Учебник, в котором демонстрируется функциональное преобразование.</span><span class="sxs-lookup"><span data-stu-id="23e0c-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="23e0c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="23e0c-120">See Also</span></span>  
 [<span data-ttu-id="23e0c-121">Выполнение запросов деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23e0c-121">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
