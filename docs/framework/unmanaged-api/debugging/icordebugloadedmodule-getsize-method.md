---
title: "Метод ICorDebugLoadedModule::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29adc45df57c5f31c299dc28b611bcf0599d4aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="d6c9c-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="d6c9c-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="d6c9c-103">Возвращает размер загруженного модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6c9c-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6c9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6c9c-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="d6c9c-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6c9c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6c9c-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6c9c-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d6c9c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c9c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d6c9c-109">Requirements</span></span>  
 <span data-ttu-id="d6c9c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6c9c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c9c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6c9c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6c9c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6c9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6c9c-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c9c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c9c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d6c9c-114">See Also</span></span>  
 [<span data-ttu-id="d6c9c-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="d6c9c-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="d6c9c-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d6c9c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
