---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 8af814ff2eaaf3ae6dae9031c13bf37ea0c1236b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122654"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="9bc88-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="9bc88-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="9bc88-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="9bc88-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bc88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bc88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bc88-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="9bc88-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="9bc88-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bc88-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="9bc88-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bc88-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9bc88-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc88-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9bc88-109">Requirements</span></span>  
 <span data-ttu-id="9bc88-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bc88-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc88-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bc88-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bc88-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bc88-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bc88-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc88-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc88-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9bc88-114">See also</span></span>

- [<span data-ttu-id="9bc88-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="9bc88-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="9bc88-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9bc88-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
