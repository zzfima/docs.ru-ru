---
title: "Метод ICorDebugMemoryBuffer::GetStartAddress"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 97c08e87f63b36bfee5ade75e44f4867441bee92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="b703c-102">Метод ICorDebugMemoryBuffer::GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="b703c-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="b703c-103">Возвращает начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="b703c-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b703c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b703c-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b703c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b703c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b703c-106">[out] Указатель на начальный адрес буфера памяти.</span><span class="sxs-lookup"><span data-stu-id="b703c-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b703c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b703c-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b703c-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b703c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b703c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b703c-109">Requirements</span></span>  
 <span data-ttu-id="b703c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b703c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b703c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b703c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b703c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b703c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b703c-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b703c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b703c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b703c-114">See Also</span></span>  
 [<span data-ttu-id="b703c-115">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="b703c-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="b703c-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b703c-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
