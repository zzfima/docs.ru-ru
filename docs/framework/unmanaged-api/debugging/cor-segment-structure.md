---
title: "Структура COR_SEGMENT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc7a749f92149d7f0f5725aec6d90d72e0582c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corsegment-structure"></a><span data-ttu-id="3e613-102">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="3e613-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="3e613-103">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="3e613-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e613-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e613-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="3e613-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3e613-105">Members</span></span>  
  
|<span data-ttu-id="3e613-106">Член</span><span class="sxs-lookup"><span data-stu-id="3e613-106">Member</span></span>|<span data-ttu-id="3e613-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3e613-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="3e613-108">Начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="3e613-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="3e613-109">Конечный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="3e613-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="3e613-110">Объект [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) член перечисления, указывающее, создание области памяти.</span><span class="sxs-lookup"><span data-stu-id="3e613-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="3e613-111">Номер кучи, в которой находится в области памяти.</span><span class="sxs-lookup"><span data-stu-id="3e613-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="3e613-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3e613-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e613-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e613-113">Remarks</span></span>  
 <span data-ttu-id="3e613-114">`COR_SEGMENTS` Структура представляет области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="3e613-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="3e613-115">`COR_SEGMENTS`объекты являются элементами [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) объекта коллекции, который заполняется путем вызова[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="3e613-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="3e613-116">`heap` Поле является число процессоров, соответствующее кучи формируется отчет.</span><span class="sxs-lookup"><span data-stu-id="3e613-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="3e613-117">Для сборщиков мусора рабочей станции его значение всегда равно нулю, так как рабочие станции имеют только один кучи сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="3e613-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="3e613-118">Для сборщиков мусора сервера его значение соответствует кучи, подключенный к процессору.</span><span class="sxs-lookup"><span data-stu-id="3e613-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="3e613-119">Обратите внимание, что может больше или меньше мусора кучи чем фактическое процессоров из-за особенностей реализации сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="3e613-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e613-120">Требования</span><span class="sxs-lookup"><span data-stu-id="3e613-120">Requirements</span></span>  
 <span data-ttu-id="3e613-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e613-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e613-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e613-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e613-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e613-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e613-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e613-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e613-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3e613-125">See Also</span></span>  
 [<span data-ttu-id="3e613-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="3e613-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="3e613-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="3e613-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
