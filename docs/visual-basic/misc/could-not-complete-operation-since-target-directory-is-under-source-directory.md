---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 253e7ff1d457827a2e1cb9f64eae4bfa971a3798
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645877"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="f6a6b-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="f6a6b-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="f6a6b-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="f6a6b-103">A cyclic operation has failed.</span></span> <span data-ttu-id="f6a6b-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="f6a6b-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="f6a6b-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="f6a6b-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6a6b-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f6a6b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="f6a6b-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="f6a6b-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a6b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f6a6b-108">See also</span></span>
- [<span data-ttu-id="f6a6b-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="f6a6b-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="f6a6b-110">Общие сведения об отладке: Точки останова</span><span class="sxs-lookup"><span data-stu-id="f6a6b-110">Debugging Basics: Breakpoints</span></span>](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
