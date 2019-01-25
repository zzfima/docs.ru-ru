---
title: Интерфейс1 ICorDebugILFrame2
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
ms.openlocfilehash: 0996fee88d37bbc826a4e012dc44ea9005008ae4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575519"
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="0acaf-102">Интерфейс1 ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="0acaf-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="0acaf-103">Логическим расширением интерфейса ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="0acaf-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0acaf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0acaf-104">Methods</span></span>  
  
|<span data-ttu-id="0acaf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0acaf-105">Method</span></span>|<span data-ttu-id="0acaf-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0acaf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0acaf-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="0acaf-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="0acaf-108">Возвращает объект, содержащий ICorDebugTypeEnum <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="0acaf-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="0acaf-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="0acaf-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="0acaf-110">Перераспределяет отредактированную функцию, указав новое смещение MSIL.</span><span class="sxs-lookup"><span data-stu-id="0acaf-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0acaf-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0acaf-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0acaf-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0acaf-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0acaf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0acaf-113">Requirements</span></span>  
 <span data-ttu-id="0acaf-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0acaf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0acaf-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0acaf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0acaf-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0acaf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0acaf-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0acaf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acaf-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0acaf-118">See also</span></span>
- [<span data-ttu-id="0acaf-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0acaf-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
