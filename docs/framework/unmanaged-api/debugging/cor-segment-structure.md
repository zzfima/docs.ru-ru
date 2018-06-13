---
title: Структура COR_SEGMENT
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406511"
---
# <a name="corsegment-structure"></a><span data-ttu-id="fd503-102">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="fd503-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="fd503-103">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="fd503-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd503-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd503-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="fd503-105">Участники</span><span class="sxs-lookup"><span data-stu-id="fd503-105">Members</span></span>  
  
|<span data-ttu-id="fd503-106">Член</span><span class="sxs-lookup"><span data-stu-id="fd503-106">Member</span></span>|<span data-ttu-id="fd503-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fd503-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="fd503-108">Начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="fd503-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="fd503-109">Конечный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="fd503-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="fd503-110">Объект [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) член перечисления, указывающее, создание области памяти.</span><span class="sxs-lookup"><span data-stu-id="fd503-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="fd503-111">Номер кучи, в которой находится в области памяти.</span><span class="sxs-lookup"><span data-stu-id="fd503-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="fd503-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="fd503-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd503-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd503-113">Remarks</span></span>  
 <span data-ttu-id="fd503-114">`COR_SEGMENTS` Структура представляет области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="fd503-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="fd503-115">`COR_SEGMENTS` объекты являются элементами [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объекта коллекции, который заполняется путем вызова[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="fd503-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="fd503-116">`heap` Поле является число процессоров, соответствующее кучи формируется отчет.</span><span class="sxs-lookup"><span data-stu-id="fd503-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="fd503-117">Для сборщиков мусора рабочей станции его значение всегда равно нулю, так как рабочие станции имеют только один кучи сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="fd503-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="fd503-118">Для сборщиков мусора сервера его значение соответствует кучи, подключенный к процессору.</span><span class="sxs-lookup"><span data-stu-id="fd503-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="fd503-119">Обратите внимание, что может больше или меньше мусора кучи чем фактическое процессоров из-за особенностей реализации сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="fd503-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd503-120">Требования</span><span class="sxs-lookup"><span data-stu-id="fd503-120">Requirements</span></span>  
 <span data-ttu-id="fd503-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd503-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd503-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd503-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd503-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd503-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd503-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd503-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd503-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fd503-125">See Also</span></span>  
 [<span data-ttu-id="fd503-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="fd503-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="fd503-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="fd503-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
