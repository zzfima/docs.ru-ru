---
title: "Практическое руководство: вызов перегруженной процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 777df0cc81a4e0518773a0e8cc98d590d1c0cf0d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="052e7-102">Практическое руководство. Вызов перегруженной процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="052e7-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="052e7-103">Преимущество перегрузки процедуры заключается в гибкости вызова.</span><span class="sxs-lookup"><span data-stu-id="052e7-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="052e7-104">Вызывающий код может получить сведения, необходимые для передачи в процедуру и затем вызвать одну процедуры по имени, независимо от того, какие аргументы она передает.</span><span class="sxs-lookup"><span data-stu-id="052e7-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="052e7-105">Для вызова процедуры, которая имеет определенные более одной версии</span><span class="sxs-lookup"><span data-stu-id="052e7-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="052e7-106">В вызывающем коде определите, какие данные необходимо передать в процедуру.</span><span class="sxs-lookup"><span data-stu-id="052e7-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="052e7-107">Создайте вызов процедуры обычным способом, представляя данные в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="052e7-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="052e7-108">Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенные для процедуры.</span><span class="sxs-lookup"><span data-stu-id="052e7-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="052e7-109">Необходимо определить, какую версию процедуры необходимо вызвать.</span><span class="sxs-lookup"><span data-stu-id="052e7-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="052e7-110">передает управление версию, которая соответствует списку аргументов.</span><span class="sxs-lookup"><span data-stu-id="052e7-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="052e7-111">В следующем примере вызывается `post` объявление процедуры в [как: определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="052e7-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="052e7-112">Она получает идентификатор клиента, определяет, является ли он `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="052e7-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     <span data-ttu-id="052e7-113">[!code-vb[VbVbcnProcedures&#56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="052e7-113">[!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="052e7-114">[!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="052e7-114">[!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="052e7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="052e7-115">See Also</span></span>  
 <span data-ttu-id="052e7-116">[Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-116">[Procedures](./index.md) </span></span>  
<span data-ttu-id="052e7-117"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-117"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="052e7-118"> [Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-118"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="052e7-119"> [Рекомендации по устранению неполадок](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-119"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="052e7-120"> [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-120"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="052e7-121"> [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-121"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="052e7-122"> [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-122"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="052e7-123"> [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-123"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="052e7-124"> [Разрешение перегрузки](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="052e7-124"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="052e7-125"> [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="052e7-125"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
