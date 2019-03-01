---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 39373cd368282f3b109b450189561366b9e74484
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200576"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="85719-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="85719-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="85719-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="85719-103">A cyclic operation has failed.</span></span> <span data-ttu-id="85719-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="85719-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="85719-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="85719-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85719-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="85719-106">To correct this error</span></span>  
  
-   <span data-ttu-id="85719-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="85719-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85719-108">См. также</span><span class="sxs-lookup"><span data-stu-id="85719-108">See also</span></span>
- [<span data-ttu-id="85719-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="85719-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="85719-110">Использование точек останова в отладчике Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85719-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
