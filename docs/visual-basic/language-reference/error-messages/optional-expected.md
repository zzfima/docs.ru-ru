---
title: Ожидается Optional
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 0ad0d0890b73103a0678b13409a24190329d37d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266338"
---
# <a name="optional-expected"></a><span data-ttu-id="948b3-102">Ожидается Optional</span><span class="sxs-lookup"><span data-stu-id="948b3-102">'Optional' expected</span></span>
<span data-ttu-id="948b3-103">Необязательный аргумент в объявлении процедуры следует обязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="948b3-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="948b3-104">Каждый аргумент необязательного аргумента также должен быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="948b3-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="948b3-105">**Идентификатор ошибки:** BC30202</span><span class="sxs-lookup"><span data-stu-id="948b3-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="948b3-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="948b3-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="948b3-107">Если аргумент является обязательным, переместите его предшествовало первому необязательному аргументу в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="948b3-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2.  <span data-ttu-id="948b3-108">Если аргумент является необязательным, используйте `Optional` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="948b3-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948b3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="948b3-109">See also</span></span>
- [<span data-ttu-id="948b3-110">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="948b3-110">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
