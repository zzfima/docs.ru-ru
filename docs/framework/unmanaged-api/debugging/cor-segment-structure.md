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
ms.openlocfilehash: a5c743064b8ca645cf45d02b8800c88187bf4c6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179284"
---
# <a name="cor_segment-structure"></a><span data-ttu-id="aae1b-102">Структура COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="aae1b-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="aae1b-103">Содержит сведения об области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="aae1b-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aae1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aae1b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;
    CORDB_ADDRESS end;
    CorDebugGenerationTypes gen;
    ULONG heap;
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="aae1b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="aae1b-105">Members</span></span>  
  
|<span data-ttu-id="aae1b-106">Участник</span><span class="sxs-lookup"><span data-stu-id="aae1b-106">Member</span></span>|<span data-ttu-id="aae1b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aae1b-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="aae1b-108">Начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="aae1b-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="aae1b-109">Конечный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="aae1b-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="aae1b-110">Элемент перечисления [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md), который указывает на создание области памяти.</span><span class="sxs-lookup"><span data-stu-id="aae1b-110">A [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="aae1b-111">Номер кучи, в которой находится область памяти.</span><span class="sxs-lookup"><span data-stu-id="aae1b-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="aae1b-112">Дополнительные сведения см. в разделе «Примечания».</span><span class="sxs-lookup"><span data-stu-id="aae1b-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aae1b-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="aae1b-113">Remarks</span></span>  
 <span data-ttu-id="aae1b-114">Структура `COR_SEGMENTS` представляет область памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="aae1b-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="aae1b-115">Объекты `COR_SEGMENTS` являются членами объекта коллекции [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md), которая заполняется путем вызова метода [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md).</span><span class="sxs-lookup"><span data-stu-id="aae1b-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="aae1b-116">В поле `heap` указан номер обработчика, который соответствует определенной куче.</span><span class="sxs-lookup"><span data-stu-id="aae1b-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="aae1b-117">Для сборщиков мусора на рабочей станции это значение всегда равно нулю, ведь на рабочих станциях только одна куча сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="aae1b-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="aae1b-118">Для сборщиков мусора на сервере это значение соответствует обработчику, к которому привязана куча.</span><span class="sxs-lookup"><span data-stu-id="aae1b-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="aae1b-119">Куч сборки мусора может быть больше или меньше фактического числа обработчиков в связи с особенностями реализации сборщика мусора.</span><span class="sxs-lookup"><span data-stu-id="aae1b-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aae1b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="aae1b-120">Requirements</span></span>  
 <span data-ttu-id="aae1b-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aae1b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aae1b-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aae1b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aae1b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aae1b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aae1b-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aae1b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae1b-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aae1b-125">See also</span></span>

- [<span data-ttu-id="aae1b-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="aae1b-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="aae1b-127">Отладки</span><span class="sxs-lookup"><span data-stu-id="aae1b-127">Debugging</span></span>](index.md)
