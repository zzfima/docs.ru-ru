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
ms.openlocfilehash: faf1be65d308b223490f3ae67eed3d8a2b1688b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609378"
---
# <a name="corsegment-structure"></a><span data-ttu-id="201b1-102">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="201b1-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="201b1-103">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="201b1-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="201b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="201b1-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="201b1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="201b1-105">Members</span></span>  
  
|<span data-ttu-id="201b1-106">Член</span><span class="sxs-lookup"><span data-stu-id="201b1-106">Member</span></span>|<span data-ttu-id="201b1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="201b1-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="201b1-108">Начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="201b1-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="201b1-109">Конечный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="201b1-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="201b1-110">Элемент перечисления [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md), который указывает на создание области памяти.</span><span class="sxs-lookup"><span data-stu-id="201b1-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="201b1-111">Номер кучи, в которой находится область памяти.</span><span class="sxs-lookup"><span data-stu-id="201b1-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="201b1-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="201b1-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="201b1-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="201b1-113">Remarks</span></span>  
 <span data-ttu-id="201b1-114">Структура `COR_SEGMENTS` представляет область памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="201b1-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="201b1-115">Объекты `COR_SEGMENTS` являются членами объекта коллекции [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md), которая заполняется путем вызова метода [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md).</span><span class="sxs-lookup"><span data-stu-id="201b1-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="201b1-116">В поле `heap` указан номер обработчика, который соответствует определенной куче.</span><span class="sxs-lookup"><span data-stu-id="201b1-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="201b1-117">Для сборщиков мусора на рабочей станции это значение всегда равно нулю, ведь на рабочих станциях только одна куча сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="201b1-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="201b1-118">Для сборщиков мусора на сервере это значение соответствует обработчику, к которому привязана куча.</span><span class="sxs-lookup"><span data-stu-id="201b1-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="201b1-119">Куч сборки мусора может быть больше или меньше фактического числа обработчиков в связи с особенностями реализации сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="201b1-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="201b1-120">Требования</span><span class="sxs-lookup"><span data-stu-id="201b1-120">Requirements</span></span>  
 <span data-ttu-id="201b1-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="201b1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="201b1-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="201b1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="201b1-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="201b1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="201b1-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="201b1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="201b1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="201b1-125">See also</span></span>

- [<span data-ttu-id="201b1-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="201b1-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="201b1-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="201b1-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
