---
title: Операнд оператора AddressOf должен быть именем метода (без скобок)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323828"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="fb213-102">Операнд оператора AddressOf должен быть именем метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="fb213-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="fb213-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="fb213-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="fb213-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fb213-104">The syntax is as follows.</span></span>  
  
 `AddressOf` `procedurename`  
  
 <span data-ttu-id="fb213-105">Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="fb213-105">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="fb213-106">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="fb213-106">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb213-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fb213-107">To correct this error</span></span>  
  
1. <span data-ttu-id="fb213-108">Удалите круглые скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="fb213-108">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="fb213-109">Убедитесь, что аргумент является имя метода.</span><span class="sxs-lookup"><span data-stu-id="fb213-109">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb213-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fb213-110">See also</span></span>

- [<span data-ttu-id="fb213-111">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="fb213-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="fb213-112">Делегаты</span><span class="sxs-lookup"><span data-stu-id="fb213-112">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
