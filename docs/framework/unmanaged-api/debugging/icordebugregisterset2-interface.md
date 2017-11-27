---
title: "Интерфейс ICorDebugRegisterSet2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2
helpviewer_keywords: ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26967f50ded62f935a705c25eed58314b77bedd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="74b3f-102">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="74b3f-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="74b3f-103">Расширяет возможности [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) интерфейс для аппаратных платформ, имеющих более 64 регистров.</span><span class="sxs-lookup"><span data-stu-id="74b3f-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74b3f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="74b3f-104">Methods</span></span>  
  
|<span data-ttu-id="74b3f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="74b3f-105">Method</span></span>|<span data-ttu-id="74b3f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="74b3f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74b3f-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="74b3f-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="74b3f-108">Получает значение каждого регистра (на компьютере, который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="74b3f-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="74b3f-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="74b3f-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="74b3f-110">Возвращает массив байтов, предоставляющий растровое изображение доступных регистров.</span><span class="sxs-lookup"><span data-stu-id="74b3f-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="74b3f-111">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="74b3f-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="74b3f-112">Не реализовано в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="74b3f-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74b3f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="74b3f-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74b3f-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="74b3f-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74b3f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="74b3f-115">Requirements</span></span>  
 <span data-ttu-id="74b3f-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74b3f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74b3f-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74b3f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74b3f-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74b3f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74b3f-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74b3f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b3f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="74b3f-120">See Also</span></span>  
 [<span data-ttu-id="74b3f-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="74b3f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="74b3f-122">ICorDebugRegisterSet-интерфейс</span><span class="sxs-lookup"><span data-stu-id="74b3f-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
