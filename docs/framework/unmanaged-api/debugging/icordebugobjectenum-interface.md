---
title: "ICorDebugObjectEnum интерфейс1"
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
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f2610600d102177c80821c78e7d07f8aed1b6de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="9905e-102">ICorDebugObjectEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="9905e-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="9905e-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="9905e-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9905e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9905e-104">Methods</span></span>  
  
|<span data-ttu-id="9905e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9905e-105">Method</span></span>|<span data-ttu-id="9905e-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="9905e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9905e-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="9905e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="9905e-108">Получает адреса RVA для заданного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="9905e-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9905e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9905e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9905e-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9905e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9905e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9905e-111">Requirements</span></span>  
 <span data-ttu-id="9905e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9905e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9905e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9905e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9905e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9905e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9905e-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9905e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9905e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9905e-116">See Also</span></span>  
 [<span data-ttu-id="9905e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9905e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
