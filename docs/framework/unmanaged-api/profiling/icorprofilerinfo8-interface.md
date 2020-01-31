---
title: Интерфейс ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868321"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="950ba-102">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="950ba-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="950ba-103">Подкласс [ICorProfilerInfo7](icorprofilerinfo7-interface.md) , предоставляющий методы для запроса сведений о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="950ba-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="950ba-104">Методы</span><span class="sxs-lookup"><span data-stu-id="950ba-104">Methods</span></span>  

| <span data-ttu-id="950ba-105">Метод</span><span class="sxs-lookup"><span data-stu-id="950ba-105">Method</span></span>|<span data-ttu-id="950ba-106">Описание</span><span class="sxs-lookup"><span data-stu-id="950ba-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="950ba-107">Метод Исфунктиондинамик</span><span class="sxs-lookup"><span data-stu-id="950ba-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="950ba-108">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="950ba-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="950ba-109">Метод GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="950ba-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="950ba-110">Сопоставляет указатель инструкции управляемого кода с FunctionID.</span><span class="sxs-lookup"><span data-stu-id="950ba-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="950ba-111">Этот метод работает как с динамическими, так и с нединамическими методами.</span><span class="sxs-lookup"><span data-stu-id="950ba-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="950ba-112">Метод Жетдинамикфунктионинфо</span><span class="sxs-lookup"><span data-stu-id="950ba-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="950ba-113">Извлекает сведения о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="950ba-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="950ba-114">Требования</span><span class="sxs-lookup"><span data-stu-id="950ba-114">Requirements</span></span>  
<span data-ttu-id="950ba-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="950ba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="950ba-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="950ba-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="950ba-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="950ba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="950ba-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="950ba-118">See also</span></span>

- [<span data-ttu-id="950ba-119">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="950ba-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
