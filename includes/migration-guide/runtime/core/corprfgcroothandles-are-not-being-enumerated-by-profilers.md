---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858430"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="13847-101">Профилировщики не перечисляют COR_PRF_GC_ROOT_HANDLE</span><span class="sxs-lookup"><span data-stu-id="13847-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="13847-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="13847-102">Details</span></span>|<span data-ttu-id="13847-103">В .NET Framework 4.5.1 API профилирования <code>RootReferences2()</code> по ошибке никогда не возвращает <code>COR_PRF_GC_ROOT_HANDLE</code> (вместо этого возвращается <code>COR_PRF_GC_ROOT_OTHER</code>).</span><span class="sxs-lookup"><span data-stu-id="13847-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="13847-104">Эта проблема решена в .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="13847-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="13847-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="13847-105">Suggestion</span></span>|<span data-ttu-id="13847-106">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="13847-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="13847-107">Область</span><span class="sxs-lookup"><span data-stu-id="13847-107">Scope</span></span>|<span data-ttu-id="13847-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="13847-108">Minor</span></span>|
|<span data-ttu-id="13847-109">Версия</span><span class="sxs-lookup"><span data-stu-id="13847-109">Version</span></span>|<span data-ttu-id="13847-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="13847-110">4.5.1</span></span>|
|<span data-ttu-id="13847-111">Тип</span><span class="sxs-lookup"><span data-stu-id="13847-111">Type</span></span>|<span data-ttu-id="13847-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="13847-112">Runtime</span></span>|

