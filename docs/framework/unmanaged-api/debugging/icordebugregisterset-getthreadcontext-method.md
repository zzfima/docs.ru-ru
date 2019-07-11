---
title: Метод ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef7619316cae46df350bd75a2c6838828f7e9c82
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747177"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="4183f-102">Метод ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="4183f-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="4183f-103">Получает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="4183f-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4183f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4183f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4183f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4183f-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="4183f-106">[in] Размер в байтах из `context` массива.</span><span class="sxs-lookup"><span data-stu-id="4183f-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="4183f-107">[in, out] Массив байтов, составляющих Win32 `CONTEXT` структуре для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="4183f-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4183f-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4183f-108">Remarks</span></span>  
 <span data-ttu-id="4183f-109">Отладчик должен вызвать эту функцию вместо Win32 `GetThreadContext` работать, поскольку поток может находиться в состоянии «перехваченного», где контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="4183f-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="4183f-110">Данные, возвращенные предназначена для Win32 `CONTEXT` структуре для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="4183f-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="4183f-111">Для неконечных кадров, клиенты должны проверять, регистрирующий являются допустимыми с помощью [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="4183f-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4183f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4183f-112">Requirements</span></span>  
 <span data-ttu-id="4183f-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4183f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4183f-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4183f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4183f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4183f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4183f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4183f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4183f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4183f-117">See also</span></span>

- [<span data-ttu-id="4183f-118">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="4183f-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="4183f-119">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="4183f-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
