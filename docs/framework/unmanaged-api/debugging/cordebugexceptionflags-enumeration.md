---
title: Перечисление CorDebugExceptionFlags
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
ms.openlocfilehash: 6ef81e224f3573021ee96ac313ec4923928dedad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789402"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="340ce-102">Перечисление CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="340ce-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="340ce-103">Предоставляет дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="340ce-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="340ce-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="340ce-105">Участники</span><span class="sxs-lookup"><span data-stu-id="340ce-105">Members</span></span>  
  
|<span data-ttu-id="340ce-106">Член</span><span class="sxs-lookup"><span data-stu-id="340ce-106">Member</span></span>|<span data-ttu-id="340ce-107">Описание</span><span class="sxs-lookup"><span data-stu-id="340ce-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="340ce-108">Исключение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="340ce-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="340ce-109">Исключение доступно для перехвата.</span><span class="sxs-lookup"><span data-stu-id="340ce-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="340ce-110">Время исключения все еще может быть таким, что отладчик не сможет его перехватить.</span><span class="sxs-lookup"><span data-stu-id="340ce-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="340ce-111">Например, если ниже текущего обратного вызова или события исключения, возникшего в результате JIT-вложения, нет никакого управляемого кода, такое исключение не может быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="340ce-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="340ce-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="340ce-112">Remarks</span></span>  
 <span data-ttu-id="340ce-113">В более поздних версиях для этого перечисления могут быть добавлены новые значения, поэтому следует подготовить код, использующий `CorDebugExceptionFlags` для неожиданных значений.</span><span class="sxs-lookup"><span data-stu-id="340ce-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="340ce-114">Требования</span><span class="sxs-lookup"><span data-stu-id="340ce-114">Requirements</span></span>  
 <span data-ttu-id="340ce-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="340ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="340ce-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="340ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="340ce-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="340ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="340ce-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="340ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340ce-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="340ce-119">See also</span></span>

- [<span data-ttu-id="340ce-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="340ce-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
