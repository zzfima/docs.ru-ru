---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c12ea84f1a706850972b2e404ec52eea3523de7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="2c2a9-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="2c2a9-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="2c2a9-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2a9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c2a9-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c2a9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c2a9-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="2c2a9-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c2a9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2c2a9-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c2a9-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2a9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2c2a9-109">Requirements</span></span>  
 <span data-ttu-id="2c2a9-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2a9-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c2a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c2a9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c2a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c2a9-113">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2a9-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2a9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2c2a9-114">See Also</span></span>  
 [<span data-ttu-id="2c2a9-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="2c2a9-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="2c2a9-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2c2a9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
