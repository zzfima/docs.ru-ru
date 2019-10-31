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
ms.openlocfilehash: db4f9bc6277015055cbcdb509628f2862a71dbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127152"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="1bcde-102">Метод ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="1bcde-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="1bcde-103">Возвращает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="1bcde-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bcde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bcde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bcde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bcde-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="1bcde-106">окне Размер массива `context` в байтах.</span><span class="sxs-lookup"><span data-stu-id="1bcde-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="1bcde-107">[вход, выход] Массив байтов, образующих структуру Win32 `CONTEXT` для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="1bcde-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bcde-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="1bcde-108">Remarks</span></span>  
 <span data-ttu-id="1bcde-109">Отладчик должен вызвать эту функцию вместо функции Win32 `GetThreadContext`, так как поток может находиться в состоянии "перехвачено", в котором его контекст временно изменен.</span><span class="sxs-lookup"><span data-stu-id="1bcde-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="1bcde-110">Возвращаемые данные представляют собой структуру Win32 `CONTEXT` для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="1bcde-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="1bcde-111">Для неконечных кадров клиенты должны проверить, какие регистры являются допустимыми с помощью [ICorDebugRegisterSet:: жетрегистерсаваилабле](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="1bcde-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcde-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1bcde-112">Requirements</span></span>  
 <span data-ttu-id="1bcde-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcde-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcde-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bcde-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bcde-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bcde-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bcde-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bcde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcde-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1bcde-117">See also</span></span>

- [<span data-ttu-id="1bcde-118">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="1bcde-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="1bcde-119">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="1bcde-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
