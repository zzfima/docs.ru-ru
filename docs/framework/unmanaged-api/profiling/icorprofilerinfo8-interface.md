---
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 210029ed1b1c7d780f3895f975f7a72227bbea80
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973824"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="6deea-102">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="6deea-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="6deea-103">Подкласс [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) , предоставляющий методы для запроса сведений о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="6deea-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="6deea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6deea-104">Methods</span></span>  

| <span data-ttu-id="6deea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6deea-105">Method</span></span>|<span data-ttu-id="6deea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6deea-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="6deea-107">Метод Исфунктиондинамик</span><span class="sxs-lookup"><span data-stu-id="6deea-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="6deea-108">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="6deea-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="6deea-109">Метод GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="6deea-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="6deea-110">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="6deea-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="6deea-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="6deea-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="6deea-112">Метод Жетдинамикфунктионинфо</span><span class="sxs-lookup"><span data-stu-id="6deea-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="6deea-113">Извлекает сведения о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="6deea-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="6deea-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6deea-114">Requirements</span></span>  
<span data-ttu-id="6deea-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6deea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6deea-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="6deea-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="6deea-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6deea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="6deea-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6deea-118">See also</span></span>
- [<span data-ttu-id="6deea-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="6deea-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
