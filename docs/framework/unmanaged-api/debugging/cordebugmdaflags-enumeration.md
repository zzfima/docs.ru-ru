---
title: Перечисление CorDebugMDAFlags
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: c7af194351290ad937e40a2fc8b960c2c242629c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132795"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="35a20-102">Перечисление CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="35a20-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="35a20-103">Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="35a20-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35a20-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="35a20-105">Члены</span><span class="sxs-lookup"><span data-stu-id="35a20-105">Members</span></span>  
  
|<span data-ttu-id="35a20-106">Член</span><span class="sxs-lookup"><span data-stu-id="35a20-106">Member</span></span>|<span data-ttu-id="35a20-107">Описание</span><span class="sxs-lookup"><span data-stu-id="35a20-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="35a20-108">Поток, в котором был запущен MDA, был в запаздывания с момента запуска MDA.</span><span class="sxs-lookup"><span data-stu-id="35a20-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a20-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="35a20-109">Remarks</span></span>  
 <span data-ttu-id="35a20-110">Если стек вызовов больше не описывает место первоначального создания MDA, обсуждение считается *, что он*находится в недоступном месте.</span><span class="sxs-lookup"><span data-stu-id="35a20-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="35a20-111">Это необычное обстоятельство, вызванное выполнением недействительной операции потока при выходе.</span><span class="sxs-lookup"><span data-stu-id="35a20-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a20-112">Требования</span><span class="sxs-lookup"><span data-stu-id="35a20-112">Requirements</span></span>  
 <span data-ttu-id="35a20-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a20-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a20-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35a20-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35a20-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35a20-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35a20-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a20-117">См. также</span><span class="sxs-lookup"><span data-stu-id="35a20-117">See also</span></span>

- [<span data-ttu-id="35a20-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="35a20-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
