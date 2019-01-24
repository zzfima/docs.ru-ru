---
title: Недопустимое соглашение о вызовах DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 70200b38ea3d1497daa091fa407accabaf3c4eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715781"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="d0e4e-102">Недопустимое соглашение о вызовах DLL</span><span class="sxs-lookup"><span data-stu-id="d0e4e-102">Bad DLL calling convention</span></span>
<span data-ttu-id="d0e4e-103">Аргументы, переданные в библиотеку динамической компоновки (DLL) должна в точности совпадать с ожидается подпрограммой.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="d0e4e-104">Соглашения о вызовах содержат число, тип и порядок аргументов.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="d0e4e-105">Программа вызывает подпрограммы в библиотеку DLL, передан неправильный тип или количество аргументов.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0e4e-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d0e4e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d0e4e-107">Убедитесь, что все типы аргументов совпадают с теми, которые указаны в объявлении процедуры, что при вызове.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2.  <span data-ttu-id="d0e4e-108">Убедитесь, что вы передаете одинаковое количество аргументов, указанным в объявлении процедуры, который вы вызываете.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3.  <span data-ttu-id="d0e4e-109">Если программы DLL ожидает передачи аргументов по значению, убедитесь, что `ByVal` указан для этих аргументов в объявлении.</span><span class="sxs-lookup"><span data-stu-id="d0e4e-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e4e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d0e4e-110">See also</span></span>
- [<span data-ttu-id="d0e4e-111">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="d0e4e-111">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="d0e4e-112">Оператор Call</span><span class="sxs-lookup"><span data-stu-id="d0e4e-112">Call Statement</span></span>](../../../visual-basic/language-reference/statements/call-statement.md)
- [<span data-ttu-id="d0e4e-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="d0e4e-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
