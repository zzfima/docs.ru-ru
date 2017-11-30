---
title: "ICorDebugILFrame2 интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2
helpviewer_keywords: ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 759232d5c1e5bdf00c85145fa0fc3d69743c13f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2-interface1"></a><span data-ttu-id="635bd-102">ICorDebugILFrame2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="635bd-102">ICorDebugILFrame2 Interface1</span></span>
<span data-ttu-id="635bd-103">Логическое расширение интерфейса ICorDebugILFrame-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="635bd-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="635bd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="635bd-104">Methods</span></span>  
  
|<span data-ttu-id="635bd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="635bd-105">Method</span></span>|<span data-ttu-id="635bd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="635bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="635bd-107">Метод EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="635bd-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="635bd-108">Возвращает объект ICorDebugTypeEnum, содержащий <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="635bd-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="635bd-109">Метод RemapFunction</span><span class="sxs-lookup"><span data-stu-id="635bd-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="635bd-110">Перераспределяет отредактированную функцию путем указания нового смещения MSIL.</span><span class="sxs-lookup"><span data-stu-id="635bd-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="635bd-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="635bd-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="635bd-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="635bd-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635bd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="635bd-113">Requirements</span></span>  
 <span data-ttu-id="635bd-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="635bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635bd-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="635bd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="635bd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="635bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="635bd-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635bd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="635bd-118">See Also</span></span>  
 [<span data-ttu-id="635bd-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="635bd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
