---
title: Установка не поддерживается во время выполнения
ms.date: 07/20/2015
f1_keywords:
- vbrID382
ms.assetid: cb7285d3-778f-423d-a2be-88573be8ad48
ms.openlocfilehash: bf84e5dd996d32827497dec8cdc8ae78946f5502
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33638347"
---
# <a name="set-not-supported-at-run-time"></a><span data-ttu-id="44d84-102">Установка не поддерживается во время выполнения</span><span class="sxs-lookup"><span data-stu-id="44d84-102">Set not supported at run time</span></span>
<span data-ttu-id="44d84-103">Попытка задать или изменить свойство, значение которого может быть задано только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="44d84-103">You tried to set or change a property whose value can only be set at design time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44d84-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="44d84-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="44d84-105">Удалите из кода ссылку на свойство.</span><span class="sxs-lookup"><span data-stu-id="44d84-105">Remove the reference to the property from your code.</span></span>  
  
2.  <span data-ttu-id="44d84-106">Измените ссылку, чтобы значение свойства возвращалось только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="44d84-106">Change the reference to only return the value of the property at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d84-107">См. также</span><span class="sxs-lookup"><span data-stu-id="44d84-107">See Also</span></span>  
 [<span data-ttu-id="44d84-108">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="44d84-108">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
