---
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928938"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="b538c-102">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="b538c-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="b538c-103">Подкласс [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) , предоставляющий методы для запроса сведений о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="b538c-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="b538c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b538c-104">Methods</span></span>  

| <span data-ttu-id="b538c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b538c-105">Method</span></span>|<span data-ttu-id="b538c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b538c-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="b538c-107">Метод Исфунктиондинамик</span><span class="sxs-lookup"><span data-stu-id="b538c-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="b538c-108">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="b538c-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="b538c-109">Метод GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="b538c-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="b538c-110">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="b538c-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="b538c-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="b538c-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="b538c-112">Метод Жетдинамикфунктионинфо</span><span class="sxs-lookup"><span data-stu-id="b538c-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="b538c-113">Извлекает сведения о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="b538c-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b538c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b538c-114">Requirements</span></span>  
<span data-ttu-id="b538c-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b538c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b538c-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="b538c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="b538c-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b538c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b538c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b538c-118">See also</span></span>

- [<span data-ttu-id="b538c-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b538c-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
