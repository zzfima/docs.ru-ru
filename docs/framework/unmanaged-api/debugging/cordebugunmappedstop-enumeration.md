---
title: "Перечисление CorDebugUnmappedStop"
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
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5700a9a058a349ea70020bafb7d4bed73d1f53f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="5531a-102">Перечисление CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="5531a-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="5531a-103">Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.</span><span class="sxs-lookup"><span data-stu-id="5531a-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5531a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5531a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="5531a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5531a-105">Members</span></span>  
  
|<span data-ttu-id="5531a-106">Член</span><span class="sxs-lookup"><span data-stu-id="5531a-106">Member</span></span>|<span data-ttu-id="5531a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="5531a-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="5531a-108">Не останавливайте в любой тип несопоставимого кода.</span><span class="sxs-lookup"><span data-stu-id="5531a-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="5531a-109">Остановите кода пролога.</span><span class="sxs-lookup"><span data-stu-id="5531a-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="5531a-110">Остановится в коде эпилога.</span><span class="sxs-lookup"><span data-stu-id="5531a-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="5531a-111">Остановится в коде, не имеет сопоставления информации.</span><span class="sxs-lookup"><span data-stu-id="5531a-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="5531a-112">Остановится в неуправляемом коде, который не помещается в прологе, эпилога, сведения о сопоставлении нет или неуправляемой категории.</span><span class="sxs-lookup"><span data-stu-id="5531a-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="5531a-113">Остановится в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="5531a-113">Stop in unmanaged code.</span></span> <span data-ttu-id="5531a-114">Это значение допустимо только при отладке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="5531a-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="5531a-115">Останавливается во всех типах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="5531a-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5531a-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="5531a-116">Remarks</span></span>  
 <span data-ttu-id="5531a-117">Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) метод, чтобы задать флаги, указывающие несопоставимого кода, в котором будет остановлено пошаговым.</span><span class="sxs-lookup"><span data-stu-id="5531a-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5531a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5531a-118">Requirements</span></span>  
 <span data-ttu-id="5531a-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5531a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5531a-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5531a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5531a-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5531a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5531a-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5531a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5531a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5531a-123">See Also</span></span>  
 [<span data-ttu-id="5531a-124">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="5531a-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
