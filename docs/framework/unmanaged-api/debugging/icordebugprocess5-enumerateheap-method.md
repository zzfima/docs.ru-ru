---
title: Метод ICorDebugProcess5::EnumerateHeap
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b404b7762e085eb44f0bd3b448fcee9eab9a3c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103913"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="3f673-102">Метод ICorDebugProcess5::EnumerateHeap</span><span class="sxs-lookup"><span data-stu-id="3f673-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="3f673-103">Получает перечислитель для объектов в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="3f673-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f673-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f673-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f673-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f673-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="3f673-106">[out] Указатель на адрес [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейса, который представляет перечислитель для объектов, находящихся в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="3f673-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f673-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="3f673-107">Remarks</span></span>  
 <span data-ttu-id="3f673-108">Перед вызовом `ICorDebugProcess5::EnumerateHeap` метод следует вызывать [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод и проверьте значение `areGCStructuresValid` поле возвращенного [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Объект, чтобы убедиться, что в ее текущем состоянии куче сбора мусора является перечислимым.</span><span class="sxs-lookup"><span data-stu-id="3f673-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="3f673-109">Кроме того `ICorDebugProcess5::EnumerateHeap` возвращает `E_FAIL` при подключении слишком раннем этапе жизни процесса, прежде чем памяти для управляемой куче выделяется.</span><span class="sxs-lookup"><span data-stu-id="3f673-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="3f673-110">[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект интерфейс является производным от ICorDebugEnum интерфейс, который позволяет перечислять стандартный перечислитель [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="3f673-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="3f673-111">Этот метод заполняет [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) объект коллекции с [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые предоставляют сведения обо всех объектах.</span><span class="sxs-lookup"><span data-stu-id="3f673-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="3f673-112">Коллекция может также включать [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) экземпляров, которые предоставляют сведения об объектах, которые не связаны с каким-либо объекта, но еще не были собираются сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="3f673-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f673-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3f673-113">Requirements</span></span>  
 <span data-ttu-id="3f673-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f673-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f673-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f673-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f673-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f673-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3f673-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3f673-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f673-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3f673-118">See also</span></span>

- [<span data-ttu-id="3f673-119">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="3f673-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3f673-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3f673-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
