---
title: Не удается выполнить загрузку сведений для класса <classname>
ms.date: 07/20/2015
f1_keywords:
- vbc30712
- bc30712
helpviewer_keywords:
- BC30712
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
ms.openlocfilehash: 42f31df7f4bc849374d8beb09e17394c3cdd5ec4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774867"
---
# <a name="unable-to-load-information-for-class-classname"></a><span data-ttu-id="d723b-102">Не удалось загрузить сведения для класса\<имя_класса > "</span><span class="sxs-lookup"><span data-stu-id="d723b-102">Unable to load information for class '\<classname>'</span></span>
<span data-ttu-id="d723b-103">Использовалась ссылка на класс, который не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d723b-103">A reference was made to a class that is not available.</span></span>  
  
 <span data-ttu-id="d723b-104">**Идентификатор ошибки:** BC30712</span><span class="sxs-lookup"><span data-stu-id="d723b-104">**Error ID:** BC30712</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d723b-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d723b-105">To correct this error</span></span>  
  
1. <span data-ttu-id="d723b-106">Убедитесь, что класс был определен и что имя указано правильно.</span><span class="sxs-lookup"><span data-stu-id="d723b-106">Verify that the class is defined and that you spelled the name correctly.</span></span>  
  
2. <span data-ttu-id="d723b-107">Попробуйте обратиться к одному из членов, объявленных в модуле.</span><span class="sxs-lookup"><span data-stu-id="d723b-107">Try accessing one of the members declared in the module.</span></span> <span data-ttu-id="d723b-108">В некоторых случаях среда отладки не может найти члены, потому что модули, в которых они объявлены, еще не были загружены.</span><span class="sxs-lookup"><span data-stu-id="d723b-108">In some cases, the debugging environment cannot locate members because the modules where they are declared have not been loaded yet.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d723b-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d723b-109">See also</span></span>

- [<span data-ttu-id="d723b-110">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d723b-110">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
