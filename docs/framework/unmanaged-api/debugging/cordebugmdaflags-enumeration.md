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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf9f7f3d3419efc9e1dc7d75fc7272432c0cf5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739691"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="c63d5-102">Перечисление CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="c63d5-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="c63d5-103">Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="c63d5-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c63d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c63d5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c63d5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c63d5-105">Members</span></span>  
  
|<span data-ttu-id="c63d5-106">Член</span><span class="sxs-lookup"><span data-stu-id="c63d5-106">Member</span></span>|<span data-ttu-id="c63d5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c63d5-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="c63d5-108">Поток, на котором был запущен MDA перенесена, так как был запущен MDA.</span><span class="sxs-lookup"><span data-stu-id="c63d5-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c63d5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c63d5-109">Remarks</span></span>  
 <span data-ttu-id="c63d5-110">Если стек вызовов больше не описывает, где изначально был вызван MDA, поток считается *спящий режим*.</span><span class="sxs-lookup"><span data-stu-id="c63d5-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="c63d5-111">Это необычное обстоятельство при выполнении недопустимой операции при выходе из потока.</span><span class="sxs-lookup"><span data-stu-id="c63d5-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c63d5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c63d5-112">Requirements</span></span>  
 <span data-ttu-id="c63d5-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63d5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c63d5-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c63d5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c63d5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c63d5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c63d5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c63d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63d5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c63d5-117">See also</span></span>

- [<span data-ttu-id="c63d5-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c63d5-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
