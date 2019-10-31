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
ms.openlocfilehash: 583819e8e7ab16a8ac1ce72892f4353e3043ce3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129690"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="4626b-102">Метод ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="4626b-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="4626b-103">Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.</span><span class="sxs-lookup"><span data-stu-id="4626b-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4626b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4626b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4626b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4626b-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="4626b-106">окне Константа [кордебугнженполици](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) , определяющая, как приложение загружает образы в машинном кодах при работе в управляемом отладчике.</span><span class="sxs-lookup"><span data-stu-id="4626b-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4626b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="4626b-107">Remarks</span></span>  
 <span data-ttu-id="4626b-108">Если политика успешно установлена, метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="4626b-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="4626b-109">Если `ePolicy` находится за пределами диапазона перечисляемых значений, определенных параметром [кордебугнженполици](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызов метода не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="4626b-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="4626b-110">Если не удается обновить политику генератора образов в машинном код (Ngen. exe), метод возвращает `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="4626b-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="4626b-111">Метод `ICorDebugProcess5::EnableNGenPolicy` можно вызвать в любое время во время существования процесса.</span><span class="sxs-lookup"><span data-stu-id="4626b-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="4626b-112">Политика действует для всех модулей, загруженных после установки политики.</span><span class="sxs-lookup"><span data-stu-id="4626b-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4626b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4626b-113">Requirements</span></span>  
 <span data-ttu-id="4626b-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4626b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4626b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4626b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4626b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4626b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4626b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4626b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4626b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4626b-118">See also</span></span>

- [<span data-ttu-id="4626b-119">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="4626b-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="4626b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4626b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4626b-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="4626b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
