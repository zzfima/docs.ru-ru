---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5ef73be22ea79d15ec53e8ab33c34441002acce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732431"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="a939d-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="a939d-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="a939d-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="a939d-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a939d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a939d-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a939d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a939d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="a939d-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="a939d-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a939d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a939d-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a939d-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a939d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a939d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a939d-109">Requirements</span></span>  
 <span data-ttu-id="a939d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a939d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a939d-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a939d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a939d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a939d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a939d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a939d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a939d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a939d-114">See also</span></span>
- [<span data-ttu-id="a939d-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="a939d-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="a939d-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a939d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
