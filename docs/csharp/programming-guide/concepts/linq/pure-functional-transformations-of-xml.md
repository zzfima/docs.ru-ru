---
title: "Чистые функциональные преобразования XML (C#)"
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
ms.assetid: 97e8e582-eb3d-4756-bbfb-0899eb688ae4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ee60c400bb9bff719f818ab5a5a0a3c667a1b412
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pure-functional-transformations-of-xml-c"></a><span data-ttu-id="49396-102">Чистые функциональные преобразования XML (C#)</span><span class="sxs-lookup"><span data-stu-id="49396-102">Pure Functional Transformations of XML (C#)</span></span>
<span data-ttu-id="49396-103">В этом разделе приведен учебник по функциональным преобразованиям для XML.</span><span class="sxs-lookup"><span data-stu-id="49396-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="49396-104">В учебнике разъясняются основные принципы и языковые конструкции, которые необходимо понять, чтобы использовать функциональные преобразования. В нем также рассказывается об использовании функциональных преобразований для обработки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="49396-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="49396-105">Несмотря на то что в этом учебнике приведены примеры кода LINQ to XML, все базовые принципы также применяются и к другим технологиям LINQ.</span><span class="sxs-lookup"><span data-stu-id="49396-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="49396-106">В учебнике [Управление содержимым в документе WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) приведен ряд примеров, каждый из которых является продолжением предыдущего.</span><span class="sxs-lookup"><span data-stu-id="49396-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="49396-107">Эти примеры демонстрируют подход с использованием чисто функциональных преобразований для обработки XML.</span><span class="sxs-lookup"><span data-stu-id="49396-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="49396-108">Для работы с этим учебником требуются твердые знания в области C#.</span><span class="sxs-lookup"><span data-stu-id="49396-108">This tutorial assumes a working knowledge of C#.</span></span> <span data-ttu-id="49396-109">В этом учебнике не приводится подробное описание семантики и языковых конструкций, однако в нем есть ссылки на соответствующую документацию по языку.</span><span class="sxs-lookup"><span data-stu-id="49396-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="49396-110">Требуются также твердые знания базовых принципов программирования и XML, в том числе пространств имен XML.</span><span class="sxs-lookup"><span data-stu-id="49396-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49396-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="49396-111">In This Section</span></span>  
  
|<span data-ttu-id="49396-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="49396-112">Topic</span></span>|<span data-ttu-id="49396-113">Описание</span><span class="sxs-lookup"><span data-stu-id="49396-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="49396-114">Введение в чистые функциональные преобразования (C#)</span><span class="sxs-lookup"><span data-stu-id="49396-114">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)|<span data-ttu-id="49396-115">Описывает функциональные преобразования и определяет соответствующую технологию.</span><span class="sxs-lookup"><span data-stu-id="49396-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="49396-116">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="49396-116">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)|<span data-ttu-id="49396-117">Подробно описывает отложенное вычисление и отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="49396-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="49396-118">Учебник. Управление содержимым в документе WordprocessingML (C#)</span><span class="sxs-lookup"><span data-stu-id="49396-118">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="49396-119">Учебник, в котором демонстрируется функциональное преобразование.</span><span class="sxs-lookup"><span data-stu-id="49396-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49396-120">См. также</span><span class="sxs-lookup"><span data-stu-id="49396-120">See Also</span></span>  
 [<span data-ttu-id="49396-121">Выполнение запросов к деревьям XML (C#)</span><span class="sxs-lookup"><span data-stu-id="49396-121">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)

