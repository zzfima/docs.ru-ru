---
title: '&#39;Необязательный&#39; ожидается'
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 46bd84e2bcf5c5bea11a5c9d8b6e9254c49e3021
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642481"
---
# <a name="39optional39-expected"></a><span data-ttu-id="73664-102">&#39;Необязательный&#39; ожидается</span><span class="sxs-lookup"><span data-stu-id="73664-102">&#39;Optional&#39; expected</span></span>
<span data-ttu-id="73664-103">Необязательный аргумент в объявлении процедуры следует обязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="73664-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="73664-104">Каждый аргумент необязательного аргумента также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="73664-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="73664-105">**Идентификатор ошибки:** BC30202</span><span class="sxs-lookup"><span data-stu-id="73664-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73664-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="73664-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="73664-107">Если аргумент является обязательным, переместите его предшествовало первому необязательному аргументу в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="73664-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="73664-108">Если аргумент является необязательным, используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="73664-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73664-109">См. также</span><span class="sxs-lookup"><span data-stu-id="73664-109">See also</span></span>
- [<span data-ttu-id="73664-110">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="73664-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
