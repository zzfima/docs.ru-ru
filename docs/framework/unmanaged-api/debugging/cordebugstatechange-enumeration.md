---
title: "Перечисление CorDebugStateChange"
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
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da9d2bb793340aa4736e0b26ab9bf9d5ec7c546a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="7a5df-102">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="7a5df-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="7a5df-103">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="7a5df-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a5df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a5df-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="7a5df-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7a5df-105">Members</span></span>  
  
|<span data-ttu-id="7a5df-106">Член</span><span class="sxs-lookup"><span data-stu-id="7a5df-106">Member</span></span>|<span data-ttu-id="7a5df-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7a5df-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="7a5df-108">Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.</span><span class="sxs-lookup"><span data-stu-id="7a5df-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="7a5df-109">Память процесса может отличаться произвольным образом от предыдущего варианта.</span><span class="sxs-lookup"><span data-stu-id="7a5df-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a5df-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a5df-110">Remarks</span></span>  
 <span data-ttu-id="7a5df-111">Член `CorDebugStateChange` перечисление предоставляется как аргумент при вызове отладчиком [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) метод</span><span class="sxs-lookup"><span data-stu-id="7a5df-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a5df-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7a5df-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a5df-113">Требования</span><span class="sxs-lookup"><span data-stu-id="7a5df-113">Requirements</span></span>  
 <span data-ttu-id="7a5df-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a5df-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a5df-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a5df-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a5df-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a5df-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a5df-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a5df-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5df-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7a5df-118">See Also</span></span>  
 [<span data-ttu-id="7a5df-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="7a5df-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="7a5df-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="7a5df-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
