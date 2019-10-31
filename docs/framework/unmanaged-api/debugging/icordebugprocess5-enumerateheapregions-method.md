---
title: Метод ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129644"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="7fba2-102">Метод ICorDebugProcess5::EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="7fba2-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="7fba2-103">Возвращает перечислитель для диапазонов памяти управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="7fba2-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fba2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fba2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fba2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fba2-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="7fba2-106">заполняет Указатель на адрес объекта интерфейса [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) , который является перечислителем для диапазонов памяти, в которых объекты находятся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="7fba2-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fba2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="7fba2-107">Remarks</span></span>  
 <span data-ttu-id="7fba2-108">Перед вызовом метода `ICorDebugProcess5::EnumerateHeapRegions` необходимо вызвать метод [метод ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) и проверить значение поля `areGCStructuresValid` возвращенного объекта [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) , чтобы убедиться, что куча сборки мусора в ее Текущее состояние является перечислимым.</span><span class="sxs-lookup"><span data-stu-id="7fba2-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="7fba2-109">Кроме того, метод `ICorDebugProcess5::EnumerateHeapRegions` возвращает `E_FAIL`, если во время существования процесса присоединяется слишком рано, до создания областей памяти.</span><span class="sxs-lookup"><span data-stu-id="7fba2-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="7fba2-110">Этот метод гарантирует перечисление всех областей памяти, которые могут содержать управляемые объекты, но не гарантирует, что управляемые объекты фактически находятся в этих регионах.</span><span class="sxs-lookup"><span data-stu-id="7fba2-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="7fba2-111">Объект коллекции [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) может включать в себя пустые или зарезервированные регионы памяти.</span><span class="sxs-lookup"><span data-stu-id="7fba2-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="7fba2-112">Объект интерфейса [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) является стандартным перечислителем, производным от интерфейса ICorDebugEnum, который позволяет перечислять объекты [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="7fba2-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="7fba2-113">Каждый объект [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) предоставляет сведения о диапазоне памяти определенного сегмента вместе с поколением объектов в этом сегменте.</span><span class="sxs-lookup"><span data-stu-id="7fba2-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fba2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7fba2-114">Requirements</span></span>  
 <span data-ttu-id="7fba2-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fba2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fba2-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fba2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fba2-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fba2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fba2-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fba2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fba2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7fba2-119">See also</span></span>

- [<span data-ttu-id="7fba2-120">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="7fba2-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="7fba2-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7fba2-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
