---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e84d6deca0cd09cc547636007208c70ab91c1ab1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223541"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="28074-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="28074-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="28074-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="28074-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28074-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28074-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28074-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28074-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="28074-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="28074-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28074-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="28074-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28074-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="28074-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28074-109">Требования</span><span class="sxs-lookup"><span data-stu-id="28074-109">Requirements</span></span>  
 <span data-ttu-id="28074-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28074-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28074-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28074-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28074-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28074-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="28074-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="28074-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28074-114">См. также</span><span class="sxs-lookup"><span data-stu-id="28074-114">See also</span></span>

- [<span data-ttu-id="28074-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="28074-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="28074-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="28074-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
