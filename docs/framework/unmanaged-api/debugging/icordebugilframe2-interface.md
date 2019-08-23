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
ms.openlocfilehash: d02dab01eca3bd4f8ce3ae7ace7f9d4be8233dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917007"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="45591-102">Интерфейс ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="45591-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="45591-103">Логическое расширение интерфейса ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="45591-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45591-104">Методы</span><span class="sxs-lookup"><span data-stu-id="45591-104">Methods</span></span>  
  
|<span data-ttu-id="45591-105">Метод</span><span class="sxs-lookup"><span data-stu-id="45591-105">Method</span></span>|<span data-ttu-id="45591-106">Описание</span><span class="sxs-lookup"><span data-stu-id="45591-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45591-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="45591-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="45591-108">Возвращает объект ICorDebugTypeEnum, содержащий <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="45591-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="45591-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="45591-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="45591-110">Повторно сопоставляет отредактированную функцию, указывая новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="45591-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45591-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="45591-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45591-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="45591-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45591-113">Требования</span><span class="sxs-lookup"><span data-stu-id="45591-113">Requirements</span></span>  
 <span data-ttu-id="45591-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45591-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45591-115">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="45591-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45591-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="45591-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45591-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45591-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45591-118">См. также</span><span class="sxs-lookup"><span data-stu-id="45591-118">See also</span></span>

- [<span data-ttu-id="45591-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="45591-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
