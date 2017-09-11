---
title: "Операндом «AddressOf» должно быть именем метода (без скобок) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
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
ms.openlocfilehash: c4ee57896b70d8af1a7bc245bdb45521c2442fea
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="2d05b-102">Операндом «AddressOf» должно быть именем метода (без скобок)</span><span class="sxs-lookup"><span data-stu-id="2d05b-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="2d05b-103">Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на конкретную процедуру.</span><span class="sxs-lookup"><span data-stu-id="2d05b-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="2d05b-104">Синтаксис выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2d05b-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="2d05b-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="2d05b-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="2d05b-106">Вы поставили скобки вокруг аргумента `AddressOf`, которые не нужны.</span><span class="sxs-lookup"><span data-stu-id="2d05b-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="2d05b-107">**Идентификатор ошибки:** BC30577</span><span class="sxs-lookup"><span data-stu-id="2d05b-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d05b-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2d05b-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="2d05b-109">Удалите скобки вокруг аргумента `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="2d05b-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="2d05b-110">Убедитесь, что аргумент является именем метода.</span><span class="sxs-lookup"><span data-stu-id="2d05b-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d05b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2d05b-111">See Also</span></span>  
 <span data-ttu-id="2d05b-112">[Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2d05b-112">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="2d05b-113"> [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="2d05b-113"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>
