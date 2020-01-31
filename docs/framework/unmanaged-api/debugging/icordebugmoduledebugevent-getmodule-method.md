---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792908"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="e98e4-102">Метод ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="e98e4-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="e98e4-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="e98e4-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e98e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e98e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e98e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e98e4-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="e98e4-106">[out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="e98e4-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e98e4-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e98e4-107">Remarks</span></span>  
 <span data-ttu-id="e98e4-108">Можно вызвать метод [GetEventKind](icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="e98e4-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e98e4-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e98e4-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e98e4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e98e4-110">Requirements</span></span>  
 <span data-ttu-id="e98e4-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e98e4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e98e4-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e98e4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e98e4-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e98e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e98e4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e98e4-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98e4-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="e98e4-115">See also</span></span>

- [<span data-ttu-id="e98e4-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e98e4-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="e98e4-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e98e4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
