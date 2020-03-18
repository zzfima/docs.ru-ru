---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858430"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="839cc-101">Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="839cc-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="839cc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="839cc-102">Details</span></span>|<span data-ttu-id="839cc-103">В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="839cc-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="839cc-104">Эта проблема решена в .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="839cc-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="839cc-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="839cc-105">Suggestion</span></span>|<span data-ttu-id="839cc-106">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="839cc-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="839cc-107">Область</span><span class="sxs-lookup"><span data-stu-id="839cc-107">Scope</span></span>|<span data-ttu-id="839cc-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="839cc-108">Minor</span></span>|
|<span data-ttu-id="839cc-109">Version</span><span class="sxs-lookup"><span data-stu-id="839cc-109">Version</span></span>|<span data-ttu-id="839cc-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="839cc-110">4.5.1</span></span>|
|<span data-ttu-id="839cc-111">Type</span><span class="sxs-lookup"><span data-stu-id="839cc-111">Type</span></span>|<span data-ttu-id="839cc-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="839cc-112">Runtime</span></span>|
