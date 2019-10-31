---
title: 'Метод Икордебугмодуледебужевент:: module'
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 5dc26d0367d01bc8da957c3ce648c3e529dddb08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096940"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="1bfad-102">Метод Икордебугмодуледебужевент:: module</span><span class="sxs-lookup"><span data-stu-id="1bfad-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="1bfad-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1bfad-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bfad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bfad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bfad-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="1bfad-106">заполняет Указатель на адрес объекта ICorDebugModule, который представляет объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1bfad-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bfad-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="1bfad-107">Remarks</span></span>  
 <span data-ttu-id="1bfad-108">Можно вызвать метод [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="1bfad-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bfad-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="1bfad-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfad-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1bfad-110">Requirements</span></span>  
 <span data-ttu-id="1bfad-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bfad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfad-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bfad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bfad-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bfad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bfad-114">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bfad-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfad-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1bfad-115">See also</span></span>

- [<span data-ttu-id="1bfad-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="1bfad-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="1bfad-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1bfad-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
