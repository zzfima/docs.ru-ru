---
title: Интерфейс ICorDebugRegisterSet2
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da2759219901a4f49808300ea3b038b10ce2d032
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101176"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="f1a23-102">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f1a23-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="f1a23-103">Расширяет возможности [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) интерфейс для аппаратных платформ, имеющих более 64 регистров.</span><span class="sxs-lookup"><span data-stu-id="f1a23-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1a23-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f1a23-104">Methods</span></span>  
  
|<span data-ttu-id="f1a23-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f1a23-105">Method</span></span>|<span data-ttu-id="f1a23-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f1a23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1a23-107">Метод GetRegisters</span><span class="sxs-lookup"><span data-stu-id="f1a23-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="f1a23-108">Получает значение каждого из регистров (на компьютере, на который в данный момент выполняется код), который указан битовой маской.</span><span class="sxs-lookup"><span data-stu-id="f1a23-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="f1a23-109">Метод GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="f1a23-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="f1a23-110">Возвращает массив байтов, предоставляет битовую схему, доступных регистров.</span><span class="sxs-lookup"><span data-stu-id="f1a23-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="f1a23-111">Метод SetRegisters</span><span class="sxs-lookup"><span data-stu-id="f1a23-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="f1a23-112">Не реализовано в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f1a23-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1a23-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1a23-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1a23-114">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f1a23-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a23-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f1a23-115">Requirements</span></span>  
 <span data-ttu-id="f1a23-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1a23-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a23-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1a23-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1a23-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1a23-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f1a23-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f1a23-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f1a23-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a23-120">See also</span></span>

- [<span data-ttu-id="f1a23-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f1a23-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f1a23-122">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f1a23-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
