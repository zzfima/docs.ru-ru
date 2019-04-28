---
title: Перечисление CorDebugUnmappedStop
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1cea8adcd12ecb3078e4469e6b018ed49064e0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723320"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="10e21-102">Перечисление CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="10e21-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="10e21-103">Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.</span><span class="sxs-lookup"><span data-stu-id="10e21-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10e21-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="10e21-105">Участники</span><span class="sxs-lookup"><span data-stu-id="10e21-105">Members</span></span>  
  
|<span data-ttu-id="10e21-106">Член</span><span class="sxs-lookup"><span data-stu-id="10e21-106">Member</span></span>|<span data-ttu-id="10e21-107">Описание</span><span class="sxs-lookup"><span data-stu-id="10e21-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="10e21-108">Не останавливайте в любом типе неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="10e21-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="10e21-109">Остановите кода пролога.</span><span class="sxs-lookup"><span data-stu-id="10e21-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="10e21-110">Остановится в коде эпилога.</span><span class="sxs-lookup"><span data-stu-id="10e21-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="10e21-111">Остановка в коде, который не имеет сопоставления информации.</span><span class="sxs-lookup"><span data-stu-id="10e21-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="10e21-112">Остановка в неуправляемом коде, который не помещается в прологе, эпилога, сведения о сопоставлении нет или неуправляемой категории.</span><span class="sxs-lookup"><span data-stu-id="10e21-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="10e21-113">Остановка в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="10e21-113">Stop in unmanaged code.</span></span> <span data-ttu-id="10e21-114">Это значение допустимо только при отладке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="10e21-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="10e21-115">Остановите во всех типах неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="10e21-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e21-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="10e21-116">Remarks</span></span>  
 <span data-ttu-id="10e21-117">Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) метод, чтобы задать флаги, определяющие несопоставленного кода, в который будет останавливаться несопоставимого.</span><span class="sxs-lookup"><span data-stu-id="10e21-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e21-118">Требования</span><span class="sxs-lookup"><span data-stu-id="10e21-118">Requirements</span></span>  
 <span data-ttu-id="10e21-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e21-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e21-120">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10e21-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10e21-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e21-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e21-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e21-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e21-123">См. также</span><span class="sxs-lookup"><span data-stu-id="10e21-123">See also</span></span>

- [<span data-ttu-id="10e21-124">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="10e21-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
