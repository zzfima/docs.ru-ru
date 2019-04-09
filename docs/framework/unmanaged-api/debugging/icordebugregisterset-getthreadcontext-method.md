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
ms.openlocfilehash: fecbcff0fd124b94aeeecf82e23d9875c34ebb9b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091581"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="0ed85-102">Метод ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="0ed85-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="0ed85-103">Получает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="0ed85-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ed85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ed85-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ed85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ed85-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="0ed85-106">[in] Размер в байтах из `context` массива.</span><span class="sxs-lookup"><span data-stu-id="0ed85-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="0ed85-107">[in, out] Массив байтов, составляющих Win32 `CONTEXT` структуре для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="0ed85-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ed85-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ed85-108">Remarks</span></span>  
 <span data-ttu-id="0ed85-109">Отладчик должен вызвать эту функцию вместо Win32 `GetThreadContext` работать, поскольку поток может находиться в состоянии «перехваченного», где контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="0ed85-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="0ed85-110">Данные, возвращенные предназначена для Win32 `CONTEXT` структуре для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="0ed85-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="0ed85-111">Для неконечных кадров, клиенты должны проверять, регистрирующий являются допустимыми с помощью [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="0ed85-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ed85-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0ed85-112">Requirements</span></span>  
 <span data-ttu-id="0ed85-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ed85-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ed85-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ed85-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ed85-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ed85-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0ed85-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ed85-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ed85-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0ed85-117">See also</span></span>

- [<span data-ttu-id="0ed85-118">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="0ed85-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="0ed85-119">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="0ed85-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
