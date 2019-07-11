---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: debf2e9dd08f6a35801932b22fbd985e7299b79f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764360"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="d4699-102">Метод ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="d4699-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="d4699-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="d4699-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4699-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4699-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4699-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4699-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="d4699-106">[out] Указатель на адрес ICorDebugModule объект, представляющий объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="d4699-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4699-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4699-107">Remarks</span></span>  
 <span data-ttu-id="d4699-108">Можно вызвать [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод, чтобы определить, был ли модуль загрузке или выгрузке.</span><span class="sxs-lookup"><span data-stu-id="d4699-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4699-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d4699-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4699-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d4699-110">Requirements</span></span>  
 <span data-ttu-id="d4699-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4699-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4699-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4699-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4699-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4699-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4699-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4699-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4699-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d4699-115">See also</span></span>

- [<span data-ttu-id="d4699-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d4699-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="d4699-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d4699-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
