---
title: '&#39;AddressOf&#39; операнд должен быть именем метода (без скобок)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 701d86e03d9b14236eec8436d99ec40cebbbcd44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583816"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="85432-102">&#39;AddressOf&#39; операнд должен быть именем метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="85432-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="85432-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="85432-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="85432-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="85432-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="85432-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="85432-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="85432-106">Вставить круглые скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="85432-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="85432-107">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="85432-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85432-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="85432-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="85432-109">Удалите круглые скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="85432-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="85432-110">Убедитесь, что аргумент является именем метода.</span><span class="sxs-lookup"><span data-stu-id="85432-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85432-111">См. также</span><span class="sxs-lookup"><span data-stu-id="85432-111">See Also</span></span>  
 [<span data-ttu-id="85432-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="85432-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="85432-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="85432-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
