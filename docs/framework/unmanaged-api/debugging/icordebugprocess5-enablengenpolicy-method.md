---
title: "Метод ICorDebugProcess5::EnableNGENPolicy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dca0df7b0be643d53bb5b9a03bd3abbb186d69dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="ef689-102">Метод ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="ef689-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="ef689-103">Задает значение, определяющее, каким образом приложение загружает образы в машинном коде во время выполнения в отладчике управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ef689-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef689-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef689-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef689-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef689-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="ef689-106">[in] Объект [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) константа, определяющая, как приложение загружает образы в машинном коде во время выполнения в отладчике управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ef689-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef689-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef689-107">Remarks</span></span>  
 <span data-ttu-id="ef689-108">Если политика задана успешно, возвращаемое методом `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="ef689-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="ef689-109">Если `ePolicy` выходит за пределы перечислимых значений, определенных в [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызванный метод не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="ef689-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="ef689-110">Если не удается обновить политики генератором образов в машинном коде (Ngen.exe), метод возвращает `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="ef689-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="ef689-111">`ICorDebugProcess5::EnableNGenPolicy` Метод может быть вызван в любое время в течение времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="ef689-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="ef689-112">Политика действует для всех модулей, которые будут загружены после политика.</span><span class="sxs-lookup"><span data-stu-id="ef689-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef689-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ef689-113">Requirements</span></span>  
 <span data-ttu-id="ef689-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef689-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef689-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef689-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef689-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef689-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef689-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef689-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef689-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ef689-118">See Also</span></span>  
 [<span data-ttu-id="ef689-119">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="ef689-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="ef689-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ef689-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ef689-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="ef689-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
