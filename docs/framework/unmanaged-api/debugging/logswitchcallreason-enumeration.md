---
title: Перечисление LogSwitchCallReason
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba39446d9ca5164d98337e93e83725cfa503903
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515330"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="ffc3a-102">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="ffc3a-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="ffc3a-103">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ffc3a-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffc3a-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="ffc3a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ffc3a-105">Members</span></span>  
  
|<span data-ttu-id="ffc3a-106">Член</span><span class="sxs-lookup"><span data-stu-id="ffc3a-106">Member</span></span>|<span data-ttu-id="ffc3a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ffc3a-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="ffc3a-108">Был создан переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ffc3a-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="ffc3a-109">Была изменена переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ffc3a-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="ffc3a-110">Удален переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="ffc3a-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffc3a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ffc3a-111">Requirements</span></span>  
 <span data-ttu-id="ffc3a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc3a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc3a-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffc3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffc3a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffc3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffc3a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc3a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ffc3a-116">See also</span></span>
- [<span data-ttu-id="ffc3a-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="ffc3a-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
