---
title: Метод ICorDebugProcess6::DecodeEvent
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a392e236f180771a9b05526a0db569f27f6f7d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230750"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="69a1f-102">Метод ICorDebugProcess6::DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="69a1f-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="69a1f-103">Декодирует события управляемой отладки, которые были инкапсулированы в полезную нагрузку из событий отладки специально созданных собственных исключений.</span><span class="sxs-lookup"><span data-stu-id="69a1f-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69a1f-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69a1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69a1f-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="69a1f-106">[входной] Указатель на массив байтов из события отладки собственного исключения, содержащий данные о событии управляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="69a1f-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="69a1f-107">[входной] Количество элементов в массиве байтов `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="69a1f-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="69a1f-108">[in] Объект [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) член перечисления, определяющая формат события неуправляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="69a1f-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="69a1f-109">[входной] Битовое поле, которое зависит от целевой архитектуры и содержит дополнительные сведения о событии отладки.</span><span class="sxs-lookup"><span data-stu-id="69a1f-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="69a1f-110">Для систем Windows, он может быть членом [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="69a1f-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="69a1f-111">[входной] Идентификатор операционной системы для потока, в котором возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="69a1f-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="69a1f-112">[out] Указатель на адрес [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) , представляющий декодированное событие управляемой отладки.</span><span class="sxs-lookup"><span data-stu-id="69a1f-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69a1f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="69a1f-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69a1f-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="69a1f-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a1f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="69a1f-115">Requirements</span></span>  
 <span data-ttu-id="69a1f-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69a1f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a1f-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69a1f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69a1f-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69a1f-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="69a1f-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="69a1f-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="69a1f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="69a1f-120">See also</span></span>

- [<span data-ttu-id="69a1f-121">Интерфейс ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="69a1f-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="69a1f-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="69a1f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
