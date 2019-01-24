---
title: Недопустимая строка шаблона
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 3fa42632ad6d69642d7b8ec36bf2880bc10a5024
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732483"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="32b16-102">Недопустимая строка шаблона</span><span class="sxs-lookup"><span data-stu-id="32b16-102">Invalid pattern string</span></span>
<span data-ttu-id="32b16-103">Строка шаблона, указанная в операции поиска `Like` , является недопустимой.</span><span class="sxs-lookup"><span data-stu-id="32b16-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="32b16-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="32b16-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="32b16-105">Просмотрите допустимые символы для выражений списка.</span><span class="sxs-lookup"><span data-stu-id="32b16-105">Review the valid characters for list expressions.</span></span>  
  
2.  <span data-ttu-id="32b16-106">В диапазоне шаблона убедитесь, что знак в начале диапазона меньше знака в конце диапазона, как в `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="32b16-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3.  <span data-ttu-id="32b16-107">В диапазоне шаблона убедитесь, что не отсутствуют дефисы, указанные рядом друг с другом, как в `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="32b16-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4.  <span data-ttu-id="32b16-108">Завершите диапазон шаблона закрывающей скобкой.</span><span class="sxs-lookup"><span data-stu-id="32b16-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b16-109">См. также</span><span class="sxs-lookup"><span data-stu-id="32b16-109">See also</span></span>
- [<span data-ttu-id="32b16-110">Оператор Like</span><span class="sxs-lookup"><span data-stu-id="32b16-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
