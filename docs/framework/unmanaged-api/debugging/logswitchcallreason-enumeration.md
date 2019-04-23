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
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198495"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="d35ea-102">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="d35ea-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="d35ea-103">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="d35ea-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d35ea-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="d35ea-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d35ea-105">Members</span></span>  
  
|<span data-ttu-id="d35ea-106">Член</span><span class="sxs-lookup"><span data-stu-id="d35ea-106">Member</span></span>|<span data-ttu-id="d35ea-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d35ea-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="d35ea-108">Был создан переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="d35ea-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="d35ea-109">Была изменена переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="d35ea-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="d35ea-110">Удален переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="d35ea-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d35ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d35ea-111">Requirements</span></span>  
 <span data-ttu-id="d35ea-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d35ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d35ea-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d35ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d35ea-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d35ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d35ea-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d35ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d35ea-116">See also</span></span>

- [<span data-ttu-id="d35ea-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d35ea-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
