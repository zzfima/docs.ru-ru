---
title: Интерфейс ICorDebugILFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e82238fbd617d56feb5c71c6161b6fd206b8b5b6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970861"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="f791a-102">Интерфейс ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="f791a-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="f791a-103">Логическим расширением интерфейса ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="f791a-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f791a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f791a-104">Methods</span></span>  
  
|<span data-ttu-id="f791a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f791a-105">Method</span></span>|<span data-ttu-id="f791a-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f791a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f791a-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="f791a-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="f791a-108">Возвращает объект, содержащий ICorDebugTypeEnum <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="f791a-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="f791a-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="f791a-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="f791a-110">Перераспределяет отредактированную функцию, указав новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="f791a-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f791a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f791a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f791a-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f791a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f791a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f791a-113">Requirements</span></span>  
 <span data-ttu-id="f791a-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f791a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f791a-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f791a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f791a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f791a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f791a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f791a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f791a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f791a-118">See also</span></span>
- [<span data-ttu-id="f791a-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f791a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
