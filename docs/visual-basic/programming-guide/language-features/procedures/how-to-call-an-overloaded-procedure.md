---
title: Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5eca03de6b6dd2ca2b992196b1ae224f8fbf5068
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="ed999-102">Практическое руководство. Вызов перегруженной процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed999-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="ed999-103">Преимущество перегрузки процедуры заключается в гибкости вызова.</span><span class="sxs-lookup"><span data-stu-id="ed999-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="ed999-104">Вызывающий код может получить сведения, необходимые для передачи в процедуру, а затем вызвать одну процедуры по имени, независимо от того, какие аргументы, она передает.</span><span class="sxs-lookup"><span data-stu-id="ed999-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="ed999-105">Вызывать процедуру, которая имеет несколько версий определенных</span><span class="sxs-lookup"><span data-stu-id="ed999-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="ed999-106">В вызывающем коде определяют, какие данные будут переданы в процедуре.</span><span class="sxs-lookup"><span data-stu-id="ed999-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="ed999-107">Создайте вызов процедуры обычным способом, представляя данные в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="ed999-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="ed999-108">Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенное для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="ed999-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="ed999-109">Необходимо определить, какую версию процедуры необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="ed999-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="ed999-110">Visual Basic передает управление в версию, которая соответствует списку аргументов.</span><span class="sxs-lookup"><span data-stu-id="ed999-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="ed999-111">В следующем примере вызывается `post` объявление процедуры в [как: определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ed999-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="ed999-112">Она получает идентификатор клиента, определяет, является ли он `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="ed999-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ed999-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ed999-113">See Also</span></span>  
 [<span data-ttu-id="ed999-114">Процедуры</span><span class="sxs-lookup"><span data-stu-id="ed999-114">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ed999-115">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="ed999-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ed999-116">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="ed999-116">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="ed999-117">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ed999-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="ed999-118">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="ed999-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="ed999-119">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="ed999-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="ed999-120">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="ed999-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="ed999-121">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="ed999-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="ed999-122">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="ed999-122">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="ed999-123">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="ed999-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
