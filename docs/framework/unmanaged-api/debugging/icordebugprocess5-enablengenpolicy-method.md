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
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792453"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="75a31-102">Метод ICorDebugProcess5::EnableNGENPolicy</span><span class="sxs-lookup"><span data-stu-id="75a31-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="75a31-103">Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.</span><span class="sxs-lookup"><span data-stu-id="75a31-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a31-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75a31-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75a31-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75a31-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="75a31-106">окне Константа [кордебугнженполици](cordebugngenpolicy-enumeration.md) , определяющая, как приложение загружает образы в машинном кодах при работе в управляемом отладчике.</span><span class="sxs-lookup"><span data-stu-id="75a31-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75a31-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="75a31-107">Remarks</span></span>  
 <span data-ttu-id="75a31-108">Если политика успешно установлена, метод возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="75a31-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="75a31-109">Если `ePolicy` находится за пределами диапазона перечисляемых значений, определенных параметром [кордебугнженполици](cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызов метода не оказывает никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="75a31-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="75a31-110">Если не удается обновить политику генератора образов в машинном код (Ngen. exe), метод возвращает `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="75a31-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="75a31-111">Метод `ICorDebugProcess5::EnableNGenPolicy` можно вызвать в любое время во время существования процесса.</span><span class="sxs-lookup"><span data-stu-id="75a31-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="75a31-112">Политика действует для всех модулей, загруженных после установки политики.</span><span class="sxs-lookup"><span data-stu-id="75a31-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a31-113">Требования</span><span class="sxs-lookup"><span data-stu-id="75a31-113">Requirements</span></span>  
 <span data-ttu-id="75a31-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75a31-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75a31-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75a31-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75a31-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75a31-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75a31-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75a31-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75a31-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="75a31-118">See also</span></span>

- [<span data-ttu-id="75a31-119">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="75a31-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="75a31-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="75a31-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="75a31-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="75a31-121">Debugging</span></span>](index.md)
