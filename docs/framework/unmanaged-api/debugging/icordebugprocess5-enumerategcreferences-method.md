---
title: Метод ICorDebugProcess5::EnumerateGCReferences
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0845165e3200d7a5e14715cbe116ea5255aa021
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948776"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="042ee-102">Метод ICorDebugProcess5::EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="042ee-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="042ee-103">Получает перечислитель для всех объектов, которые должны быть удалены сборщиком мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="042ee-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="042ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="042ee-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="042ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="042ee-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="042ee-106">[in] Логическое значение, указывающее ли слабые ссылки, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="042ee-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="042ee-107">Если `enumerateWeakReferences` — `true`, `ppEnum` перечислитель включает строгих ссылок и слабых ссылок.</span><span class="sxs-lookup"><span data-stu-id="042ee-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="042ee-108">Если `enumerateWeakReferences` является `false`, перечислитель включает только строгих ссылок.</span><span class="sxs-lookup"><span data-stu-id="042ee-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="042ee-109">[out] Указатель на адрес [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) то есть перечислитель для объектов мусора.</span><span class="sxs-lookup"><span data-stu-id="042ee-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="042ee-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="042ee-110">Remarks</span></span>  
 <span data-ttu-id="042ee-111">Этот метод позволяет определить полную цепочку корня для любого управляемого объекта в процессе и может использоваться, чтобы определить, почему объект все еще существует.</span><span class="sxs-lookup"><span data-stu-id="042ee-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042ee-112">Требования</span><span class="sxs-lookup"><span data-stu-id="042ee-112">Requirements</span></span>  
 <span data-ttu-id="042ee-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="042ee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042ee-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="042ee-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="042ee-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="042ee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="042ee-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042ee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042ee-117">См. также</span><span class="sxs-lookup"><span data-stu-id="042ee-117">See also</span></span>

- [<span data-ttu-id="042ee-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="042ee-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="042ee-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="042ee-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
