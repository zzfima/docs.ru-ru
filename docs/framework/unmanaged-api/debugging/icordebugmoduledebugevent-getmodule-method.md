---
title: "Метод ICorDebugModuleDebugEvent::GetModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b11ab8991a9f44cf2868474a8a0f6dcc1c3308c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="1b425-102">Метод ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="1b425-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="1b425-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1b425-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b425-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b425-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b425-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b425-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="1b425-106">[out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1b425-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b425-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b425-107">Remarks</span></span>  
 <span data-ttu-id="1b425-108">Можно вызвать [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод, чтобы определить, является ли модуль был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1b425-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b425-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1b425-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b425-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1b425-110">Requirements</span></span>  
 <span data-ttu-id="1b425-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b425-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b425-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b425-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b425-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b425-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b425-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b425-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b425-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1b425-115">See Also</span></span>  
 [<span data-ttu-id="1b425-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="1b425-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="1b425-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b425-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
