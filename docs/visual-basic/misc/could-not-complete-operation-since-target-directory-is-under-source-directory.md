---
title: 'Невозможно завершить операцию: конечный каталог находится внутри исходного'
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: fca42f91f803a6b12535badcb25cc05cc3d23f6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598473"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="05e4e-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="05e4e-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="05e4e-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="05e4e-103">A cyclic operation has failed.</span></span> <span data-ttu-id="05e4e-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="05e4e-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="05e4e-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="05e4e-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="05e4e-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="05e4e-106">To correct this error</span></span>  
  
- <span data-ttu-id="05e4e-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="05e4e-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e4e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="05e4e-108">See also</span></span>

- [<span data-ttu-id="05e4e-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="05e4e-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="05e4e-110">Использование точек останова в отладчике Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05e4e-110">Use breakpoints in the Visual Studio debugger</span></span>](/visualstudio/debugger/using-breakpoints)
