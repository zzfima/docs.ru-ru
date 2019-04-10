---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 71a25784f357a7e596093b314ed5b3d721d6f92c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59341885"
---
# <a name="optional-expected"></a><span data-ttu-id="edcee-102">Ожидается Optional</span><span class="sxs-lookup"><span data-stu-id="edcee-102">'Optional' expected</span></span>
<span data-ttu-id="edcee-103">Необязательный аргумент в объявлении процедуры следует обязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="edcee-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="edcee-104">Каждый аргумент необязательного аргумента также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="edcee-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="edcee-105">**Идентификатор ошибки:** BC30202</span><span class="sxs-lookup"><span data-stu-id="edcee-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="edcee-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="edcee-106">To correct this error</span></span>  
  
1. <span data-ttu-id="edcee-107">Если аргумент является обязательным, переместите его предшествовало первому необязательному аргументу в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="edcee-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="edcee-108">Если аргумент является необязательным, используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="edcee-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcee-109">См. также</span><span class="sxs-lookup"><span data-stu-id="edcee-109">See also</span></span>

- [<span data-ttu-id="edcee-110">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="edcee-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
