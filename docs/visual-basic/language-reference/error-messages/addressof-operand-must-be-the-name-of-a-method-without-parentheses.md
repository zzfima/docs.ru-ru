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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323828"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="d08ad-102">Операнд оператора AddressOf должен быть именем метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="d08ad-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="d08ad-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="d08ad-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="d08ad-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d08ad-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="d08ad-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="d08ad-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="d08ad-106">Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="d08ad-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="d08ad-107">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="d08ad-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d08ad-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d08ad-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d08ad-109">Удалите круглые скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="d08ad-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="d08ad-110">Убедитесь, что аргумент является имя метода.</span><span class="sxs-lookup"><span data-stu-id="d08ad-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d08ad-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d08ad-111">See also</span></span>

- [<span data-ttu-id="d08ad-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="d08ad-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="d08ad-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="d08ad-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
