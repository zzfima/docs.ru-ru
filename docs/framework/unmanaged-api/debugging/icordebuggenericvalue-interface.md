---
title: "ICorDebugGenericValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6c6fb4893edf0bcda9d6f7ddbeea7054f5b4fd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="292d9-102">ICorDebugGenericValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="292d9-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="292d9-103">Подкласс «ICorDebugValue», которая применяется ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="292d9-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="292d9-104">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="292d9-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="292d9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="292d9-105">Methods</span></span>  
  
|<span data-ttu-id="292d9-106">Метод</span><span class="sxs-lookup"><span data-stu-id="292d9-106">Method</span></span>|<span data-ttu-id="292d9-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="292d9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="292d9-108">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="292d9-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="292d9-109">Копирует значение в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="292d9-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="292d9-110">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="292d9-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="292d9-111">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="292d9-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="292d9-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="292d9-112">Remarks</span></span>  
 <span data-ttu-id="292d9-113">`ICorDebugGenericValue`представляет собой вложенный интерфейс, так как это не может быть удаленным.</span><span class="sxs-lookup"><span data-stu-id="292d9-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="292d9-114">Для ссылочных типов значение является ссылкой, а не ссылки на содержимое.</span><span class="sxs-lookup"><span data-stu-id="292d9-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="292d9-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="292d9-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="292d9-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="292d9-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="292d9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="292d9-117">Requirements</span></span>  
 <span data-ttu-id="292d9-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="292d9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="292d9-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="292d9-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="292d9-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="292d9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="292d9-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="292d9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292d9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="292d9-122">See Also</span></span>  
    
 [<span data-ttu-id="292d9-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="292d9-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
