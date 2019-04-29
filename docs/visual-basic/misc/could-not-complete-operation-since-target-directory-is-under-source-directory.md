---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: f53ad664b341d4db803dee1f0f008c3918d13d93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970122"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="765e4-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="765e4-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="765e4-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="765e4-103">A cyclic operation has failed.</span></span> <span data-ttu-id="765e4-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="765e4-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="765e4-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="765e4-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="765e4-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="765e4-106">To correct this error</span></span>  
  
- <span data-ttu-id="765e4-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="765e4-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765e4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="765e4-108">See also</span></span>

- [<span data-ttu-id="765e4-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="765e4-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="765e4-110">Использование точек останова в отладчике Visual Studio</span><span class="sxs-lookup"><span data-stu-id="765e4-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
