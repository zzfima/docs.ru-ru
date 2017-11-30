---
title: "Перечисление LogSwitchCallReason"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LogSwitchCallReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: LogSwitchCallReason
helpviewer_keywords: LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 937b26efa79605b585c420db608a938b3ee71f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="696fd-102">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="696fd-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="696fd-103">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="696fd-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="696fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="696fd-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="696fd-105">Члены</span><span class="sxs-lookup"><span data-stu-id="696fd-105">Members</span></span>  
  
|<span data-ttu-id="696fd-106">Член</span><span class="sxs-lookup"><span data-stu-id="696fd-106">Member</span></span>|<span data-ttu-id="696fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="696fd-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="696fd-108">Был создан переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="696fd-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="696fd-109">Была изменена переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="696fd-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="696fd-110">Удалено переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="696fd-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="696fd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="696fd-111">Requirements</span></span>  
 <span data-ttu-id="696fd-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="696fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696fd-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="696fd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="696fd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="696fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="696fd-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696fd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="696fd-116">See Also</span></span>  
 [<span data-ttu-id="696fd-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="696fd-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
