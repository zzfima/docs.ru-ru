---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788447"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="5383d-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="5383d-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="5383d-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="5383d-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5383d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5383d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5383d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5383d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5383d-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="5383d-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5383d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="5383d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5383d-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5383d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5383d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5383d-109">Requirements</span></span>  
 <span data-ttu-id="5383d-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5383d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5383d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5383d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5383d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5383d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5383d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5383d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5383d-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="5383d-114">See also</span></span>

- [<span data-ttu-id="5383d-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="5383d-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="5383d-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5383d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
