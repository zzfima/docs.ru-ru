---
title: Установка не поддерживается во время выполнения
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: 1b3f8aa3811baae240e6baa546082d0dcf2cf667
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325869"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="6171f-102">Установка не поддерживается во время выполнения</span><span class="sxs-lookup"><span data-stu-id="6171f-102">Set not supported at run time</span></span>
<span data-ttu-id="6171f-103">Попытка задать или изменить свойство, значение которого может быть задано только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="6171f-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6171f-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6171f-104">To correct this error</span></span>  
  
1. <span data-ttu-id="6171f-105">Удалите из кода ссылку на свойство.</span><span class="sxs-lookup"><span data-stu-id="6171f-105">Remove the reference to the property from your code.</span></span>  
  
2. <span data-ttu-id="6171f-106">Измените ссылку, чтобы значение свойства возвращалось только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="6171f-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6171f-107">См. также</span><span class="sxs-lookup"><span data-stu-id="6171f-107">See also</span></span>

- [<span data-ttu-id="6171f-108">Управление свойствами проекта и решения</span><span class="sxs-lookup"><span data-stu-id="6171f-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
