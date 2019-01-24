---
title: Как выполнить Вызов перегруженной процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 8320bc550c818fd2bea53f75107709eab8456096
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706421"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="ef80c-102">Как выполнить Вызов перегруженной процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef80c-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="ef80c-103">Преимущество перегрузки процедуры заключается в гибкости вызова.</span><span class="sxs-lookup"><span data-stu-id="ef80c-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="ef80c-104">Вызывающий код может получить информацию, которую необходимо передать в процедуру, а затем вызвать одну процедуры по имени, независимо от того, какие аргументы, она передает.</span><span class="sxs-lookup"><span data-stu-id="ef80c-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="ef80c-105">Для вызова процедуры, которая имеет более одной версии определенные</span><span class="sxs-lookup"><span data-stu-id="ef80c-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="ef80c-106">В вызывающем коде определите, какие данные, передаваемые в процедуру.</span><span class="sxs-lookup"><span data-stu-id="ef80c-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="ef80c-107">Создайте вызов процедуры обычным способом, представляя данные в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="ef80c-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="ef80c-108">Убедитесь, что аргументы совпадает со списком параметров в одной из версий, определенные для процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef80c-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="ef80c-109">У вас нет определить, какую версию для вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef80c-109">You do not have to determine which version of the procedure to call.</span></span> <span data-ttu-id="ef80c-110">Visual Basic передает управление версию, которая соответствует списку аргументов.</span><span class="sxs-lookup"><span data-stu-id="ef80c-110">Visual Basic passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="ef80c-111">В следующем примере вызывается `post` объявление процедуры в [как: Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ef80c-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="ef80c-112">Она получает идентификатор клиента, определяет, является ли `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="ef80c-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ef80c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ef80c-113">See also</span></span>
- [<span data-ttu-id="ef80c-114">Процедуры</span><span class="sxs-lookup"><span data-stu-id="ef80c-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ef80c-115">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="ef80c-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ef80c-116">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="ef80c-116">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="ef80c-117">Рекомендации по устранению неполадок</span><span class="sxs-lookup"><span data-stu-id="ef80c-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="ef80c-118">Практическое руководство. Определение различных версий процедуры</span><span class="sxs-lookup"><span data-stu-id="ef80c-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="ef80c-119">Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр</span><span class="sxs-lookup"><span data-stu-id="ef80c-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="ef80c-120">Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров</span><span class="sxs-lookup"><span data-stu-id="ef80c-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="ef80c-121">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="ef80c-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="ef80c-122">Разрешение перегрузки</span><span class="sxs-lookup"><span data-stu-id="ef80c-122">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="ef80c-123">Перегрузки</span><span class="sxs-lookup"><span data-stu-id="ef80c-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
