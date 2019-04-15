---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235451"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="7c6ec-101">Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="7c6ec-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7c6ec-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7c6ec-102">Details</span></span>|<span data-ttu-id="7c6ec-103">В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="7c6ec-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="7c6ec-104">Эта проблема решена в .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="7c6ec-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="7c6ec-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="7c6ec-105">Suggestion</span></span>|<span data-ttu-id="7c6ec-106">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c6ec-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="7c6ec-107">Область</span><span class="sxs-lookup"><span data-stu-id="7c6ec-107">Scope</span></span>|<span data-ttu-id="7c6ec-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="7c6ec-108">Minor</span></span>|
|<span data-ttu-id="7c6ec-109">Версия</span><span class="sxs-lookup"><span data-stu-id="7c6ec-109">Version</span></span>|<span data-ttu-id="7c6ec-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7c6ec-110">4.5.1</span></span>|
|<span data-ttu-id="7c6ec-111">Тип</span><span class="sxs-lookup"><span data-stu-id="7c6ec-111">Type</span></span>|<span data-ttu-id="7c6ec-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7c6ec-112">Runtime</span></span>|
