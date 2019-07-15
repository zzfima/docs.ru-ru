---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858402"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="3f31d-101">Значения NULL операции объединения отображаются в отладчике с запаздыванием на один шаг</span><span class="sxs-lookup"><span data-stu-id="3f31d-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3f31d-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3f31d-102">Details</span></span>|<span data-ttu-id="3f31d-103">Из-за ошибки в .NET Framework 4.5 значения, заданные с использованием операции объединения NULL, не отображаются в отладчике немедленно после выполнения операции присваивания в 64-разрядной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="3f31d-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="3f31d-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="3f31d-104">Suggestion</span></span>|<span data-ttu-id="3f31d-105">После выполнения одного дополнительного шага в отладчике локальные значения или значения поля корректно обновляются.</span><span class="sxs-lookup"><span data-stu-id="3f31d-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="3f31d-106">Эта проблема также была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="3f31d-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="3f31d-107">Область</span><span class="sxs-lookup"><span data-stu-id="3f31d-107">Scope</span></span>|<span data-ttu-id="3f31d-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="3f31d-108">Edge</span></span>|
|<span data-ttu-id="3f31d-109">Версия</span><span class="sxs-lookup"><span data-stu-id="3f31d-109">Version</span></span>|<span data-ttu-id="3f31d-110">4.5</span><span class="sxs-lookup"><span data-stu-id="3f31d-110">4.5</span></span>|
|<span data-ttu-id="3f31d-111">Тип</span><span class="sxs-lookup"><span data-stu-id="3f31d-111">Type</span></span>|<span data-ttu-id="3f31d-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3f31d-112">Runtime</span></span>|

