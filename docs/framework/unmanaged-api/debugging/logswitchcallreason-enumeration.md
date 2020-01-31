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
ms.openlocfilehash: 29781666c106755f96f945325e3a8953bf93b211
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790346"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="0d703-102">Перечисление LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="0d703-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="0d703-103">Указывает операцию, выполненную на переключателе отладки и трассировки.</span><span class="sxs-lookup"><span data-stu-id="0d703-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d703-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d703-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="0d703-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0d703-105">Members</span></span>  
  
|<span data-ttu-id="0d703-106">Член</span><span class="sxs-lookup"><span data-stu-id="0d703-106">Member</span></span>|<span data-ttu-id="0d703-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0d703-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="0d703-108">Был создан переключатель отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="0d703-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="0d703-109">Изменен параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="0d703-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="0d703-110">Удален параметр отладки/трассировки.</span><span class="sxs-lookup"><span data-stu-id="0d703-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d703-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0d703-111">Requirements</span></span>  
 <span data-ttu-id="0d703-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d703-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d703-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d703-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d703-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d703-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d703-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d703-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d703-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0d703-116">See also</span></span>

- [<span data-ttu-id="0d703-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0d703-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
