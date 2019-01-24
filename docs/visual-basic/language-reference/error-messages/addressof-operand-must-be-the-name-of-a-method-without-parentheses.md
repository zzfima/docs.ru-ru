---
title: '&#39;AddressOf&#39; операнд должен иметь имя метода (без скобок)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 6f9827d885996ffab8bdab91d0f774a57073e4a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565154"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="9912b-102">&#39;AddressOf&#39; операнд должен иметь имя метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="9912b-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="9912b-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="9912b-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="9912b-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9912b-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="9912b-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="9912b-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="9912b-106">Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="9912b-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="9912b-107">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="9912b-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9912b-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9912b-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="9912b-109">Удалите круглые скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="9912b-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="9912b-110">Убедитесь, что аргумент является имя метода.</span><span class="sxs-lookup"><span data-stu-id="9912b-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9912b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9912b-111">See also</span></span>
- [<span data-ttu-id="9912b-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="9912b-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="9912b-113">Делегаты</span><span class="sxs-lookup"><span data-stu-id="9912b-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
