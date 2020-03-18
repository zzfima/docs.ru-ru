---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858402"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="9ff81-101">Значения NULL операции объединения отображаются в отладчике с запаздыванием на один шаг</span><span class="sxs-lookup"><span data-stu-id="9ff81-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9ff81-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="9ff81-102">Details</span></span>|<span data-ttu-id="9ff81-103">Из-за ошибки в .NET Framework 4.5 значения, заданные с использованием операции объединения NULL, не отображаются в отладчике немедленно после выполнения операции присваивания в 64-разрядной версии платформы.</span><span class="sxs-lookup"><span data-stu-id="9ff81-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="9ff81-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="9ff81-104">Suggestion</span></span>|<span data-ttu-id="9ff81-105">После выполнения одного дополнительного шага в отладчике локальные значения или значения поля корректно обновляются.</span><span class="sxs-lookup"><span data-stu-id="9ff81-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="9ff81-106">Эта проблема также была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="9ff81-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="9ff81-107">Область</span><span class="sxs-lookup"><span data-stu-id="9ff81-107">Scope</span></span>|<span data-ttu-id="9ff81-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="9ff81-108">Edge</span></span>|
|<span data-ttu-id="9ff81-109">Version</span><span class="sxs-lookup"><span data-stu-id="9ff81-109">Version</span></span>|<span data-ttu-id="9ff81-110">4,5</span><span class="sxs-lookup"><span data-stu-id="9ff81-110">4.5</span></span>|
|<span data-ttu-id="9ff81-111">Type</span><span class="sxs-lookup"><span data-stu-id="9ff81-111">Type</span></span>|<span data-ttu-id="9ff81-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="9ff81-112">Runtime</span></span>|
