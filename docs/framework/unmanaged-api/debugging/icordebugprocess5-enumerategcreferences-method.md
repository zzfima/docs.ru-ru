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
ms.openlocfilehash: a97c14d83f99c847bb8569a33e175ab6eb5bccd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178624"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="09c55-102">Метод ICorDebugProcess5::EnumerateGCReferences</span><span class="sxs-lookup"><span data-stu-id="09c55-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="09c55-103">Получает регистратор для всех объектов, которые должны быть собраны мусором в процессе.</span><span class="sxs-lookup"><span data-stu-id="09c55-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09c55-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09c55-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09c55-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="09c55-106">(в) Значение Boolean, которое указывает, должны ли также перечисляться слабые ссылки.</span><span class="sxs-lookup"><span data-stu-id="09c55-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="09c55-107">Если `enumerateWeakReferences` `true`это `ppEnum` так, то перечисление включает в себя как сильные ссылки, так и слабые ссылки.</span><span class="sxs-lookup"><span data-stu-id="09c55-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="09c55-108">Если `enumerateWeakReferences` `false`это так, то перечисление включает только сильные ссылки.</span><span class="sxs-lookup"><span data-stu-id="09c55-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="09c55-109">(ваут) Указатель на адрес [ICorDebugGCReferenceEnum,](icordebuggcreferenceenum-interface.md) который является регистратором для объектов, которые будут собраны мусором.</span><span class="sxs-lookup"><span data-stu-id="09c55-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09c55-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="09c55-110">Remarks</span></span>  
 <span data-ttu-id="09c55-111">Этот метод позволяет определить полную цепочку укоренения для любого управляемого объекта в процессе и может быть использован для определения того, почему объект все еще жив.</span><span class="sxs-lookup"><span data-stu-id="09c55-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c55-112">Требования</span><span class="sxs-lookup"><span data-stu-id="09c55-112">Requirements</span></span>  
 <span data-ttu-id="09c55-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c55-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c55-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09c55-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09c55-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09c55-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09c55-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09c55-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c55-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="09c55-117">See also</span></span>

- [<span data-ttu-id="09c55-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="09c55-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="09c55-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="09c55-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
