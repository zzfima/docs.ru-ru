---
title: "ICorDebugGenericValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="8d93e-102">ICorDebugGenericValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="8d93e-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="8d93e-103">Подкласс «ICorDebugValue», которая применяется ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="8d93e-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="8d93e-104">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="8d93e-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d93e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8d93e-105">Methods</span></span>  
  
|<span data-ttu-id="8d93e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8d93e-106">Method</span></span>|<span data-ttu-id="8d93e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8d93e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d93e-108">GetValue-метод</span><span class="sxs-lookup"><span data-stu-id="8d93e-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="8d93e-109">Копирует значение в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="8d93e-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="8d93e-110">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="8d93e-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="8d93e-111">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="8d93e-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d93e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d93e-112">Remarks</span></span>  
 <span data-ttu-id="8d93e-113">`ICorDebugGenericValue`представляет собой вложенный интерфейс, так как это не может быть удаленным.</span><span class="sxs-lookup"><span data-stu-id="8d93e-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="8d93e-114">Для ссылочных типов значение является ссылкой, а не ссылки на содержимое.</span><span class="sxs-lookup"><span data-stu-id="8d93e-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="8d93e-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8d93e-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d93e-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8d93e-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d93e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8d93e-117">Requirements</span></span>  
 <span data-ttu-id="8d93e-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d93e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d93e-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d93e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d93e-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d93e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d93e-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d93e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d93e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8d93e-122">See Also</span></span>  
    
 [<span data-ttu-id="8d93e-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8d93e-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
