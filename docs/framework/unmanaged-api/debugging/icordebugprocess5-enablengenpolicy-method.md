---
title: Метод ICorDebugProcess5::EnableNGENPolicy
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca656aeba04526164a65760af990455965c5288e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665218"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="c310a-102">Метод ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="c310a-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="c310a-103">Задает значение, определяющее, каким образом приложение загружает образы в машинном коде во время работы под контролем управляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="c310a-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c310a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c310a-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c310a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c310a-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="c310a-106">[in] Объект [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) константа, определяющая, как приложение загружает образы в машинном коде во время работы под контролем управляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="c310a-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c310a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c310a-107">Remarks</span></span>  
 <span data-ttu-id="c310a-108">Если политики установлено успешно, метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="c310a-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="c310a-109">Если `ePolicy` находится вне диапазона значений перечисления, определенных в [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызов метода не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="c310a-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="c310a-110">Если невозможно обновить политику генератором машинных образов (Ngen.exe), метод возвращает `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="c310a-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="c310a-111">`ICorDebugProcess5::EnableNGenPolicy` Метод может вызываться в любое время в течение времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="c310a-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="c310a-112">Политика действует для каких-либо модулей, которые будут загружены после набора политик.</span><span class="sxs-lookup"><span data-stu-id="c310a-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c310a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c310a-113">Requirements</span></span>  
 <span data-ttu-id="c310a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c310a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c310a-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c310a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c310a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c310a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c310a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c310a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c310a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c310a-118">See also</span></span>
- [<span data-ttu-id="c310a-119">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="c310a-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="c310a-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c310a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c310a-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="c310a-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
