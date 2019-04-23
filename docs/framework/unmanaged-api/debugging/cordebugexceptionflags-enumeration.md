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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7b9b25673685dde8b75702c80f525515917ae1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078711"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="87359-102">Перечисление CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="87359-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="87359-103">Предоставляет дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="87359-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87359-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87359-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="87359-105">Участники</span><span class="sxs-lookup"><span data-stu-id="87359-105">Members</span></span>  
  
|<span data-ttu-id="87359-106">Член</span><span class="sxs-lookup"><span data-stu-id="87359-106">Member</span></span>|<span data-ttu-id="87359-107">Описание</span><span class="sxs-lookup"><span data-stu-id="87359-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="87359-108">Исключение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="87359-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="87359-109">Исключение доступно для перехвата.</span><span class="sxs-lookup"><span data-stu-id="87359-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="87359-110">Время исключения все еще может быть таким, что отладчик не сможет его перехватить.</span><span class="sxs-lookup"><span data-stu-id="87359-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="87359-111">Например, если ниже текущего обратного вызова или события исключения, возникшего в результате JIT-вложения, нет никакого управляемого кода, такое исключение не может быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="87359-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87359-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="87359-112">Remarks</span></span>  
 <span data-ttu-id="87359-113">В более поздних версиях для этого перечисления могут быть добавлены новые значения, поэтому следует подготовить код, использующий `CorDebugExceptionFlags` для неожиданных значений.</span><span class="sxs-lookup"><span data-stu-id="87359-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87359-114">Требования</span><span class="sxs-lookup"><span data-stu-id="87359-114">Requirements</span></span>  
 <span data-ttu-id="87359-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87359-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87359-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87359-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87359-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87359-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87359-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87359-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87359-119">См. также</span><span class="sxs-lookup"><span data-stu-id="87359-119">See also</span></span>

- [<span data-ttu-id="87359-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="87359-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
