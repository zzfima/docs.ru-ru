---
title: "Перечисление CorDebugStateChange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStateChange
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: caf49621342be0ff85ac3cb56b95bb87f524c3be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="680dc-102">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="680dc-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="680dc-103">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="680dc-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="680dc-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="680dc-105">Члены</span><span class="sxs-lookup"><span data-stu-id="680dc-105">Members</span></span>  
  
|<span data-ttu-id="680dc-106">Член</span><span class="sxs-lookup"><span data-stu-id="680dc-106">Member</span></span>|<span data-ttu-id="680dc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="680dc-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="680dc-108">Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.</span><span class="sxs-lookup"><span data-stu-id="680dc-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="680dc-109">Память процесса может отличаться произвольным образом от предыдущего варианта.</span><span class="sxs-lookup"><span data-stu-id="680dc-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="680dc-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="680dc-110">Remarks</span></span>  
 <span data-ttu-id="680dc-111">Член `CorDebugStateChange` перечисление предоставляется как аргумент при вызове отладчиком [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) метод</span><span class="sxs-lookup"><span data-stu-id="680dc-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="680dc-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="680dc-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="680dc-113">Требования</span><span class="sxs-lookup"><span data-stu-id="680dc-113">Requirements</span></span>  
 <span data-ttu-id="680dc-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="680dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="680dc-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="680dc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="680dc-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="680dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="680dc-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="680dc-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680dc-118">См. также</span><span class="sxs-lookup"><span data-stu-id="680dc-118">See Also</span></span>  
 [<span data-ttu-id="680dc-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="680dc-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="680dc-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="680dc-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
