---
title: "ICorDebugObjectEnum интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectEnum
helpviewer_keywords: ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: baa8ea056c457455482a5f7631956f7edce0ac91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="b8cff-102">ICorDebugObjectEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="b8cff-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="b8cff-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="b8cff-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8cff-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b8cff-104">Methods</span></span>  
  
|<span data-ttu-id="b8cff-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b8cff-105">Method</span></span>|<span data-ttu-id="b8cff-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b8cff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8cff-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b8cff-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="b8cff-108">Получает адреса RVA для заданного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b8cff-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8cff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8cff-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8cff-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b8cff-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8cff-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b8cff-111">Requirements</span></span>  
 <span data-ttu-id="b8cff-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8cff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8cff-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8cff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8cff-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8cff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8cff-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8cff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8cff-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b8cff-116">See Also</span></span>  
 [<span data-ttu-id="b8cff-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b8cff-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
