---
title: Операнд оператора AddressOf должен быть именем метода (без скобок)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 37b02ab76730458b757835fda37b8cb145ed93ad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262118"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="34204-102">Операнд оператора AddressOf должен быть именем метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="34204-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="34204-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="34204-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="34204-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="34204-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="34204-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="34204-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="34204-106">Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="34204-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="34204-107">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="34204-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="34204-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="34204-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="34204-109">Удалите круглые скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="34204-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="34204-110">Убедитесь, что аргумент является имя метода.</span><span class="sxs-lookup"><span data-stu-id="34204-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34204-111">См. также</span><span class="sxs-lookup"><span data-stu-id="34204-111">See also</span></span>
- [<span data-ttu-id="34204-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="34204-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="34204-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="34204-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
