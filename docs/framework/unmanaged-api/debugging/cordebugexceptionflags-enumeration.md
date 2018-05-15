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
ms.openlocfilehash: d963a478ee7ae42159a0eb8a4b41cf20ae663aa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="9a6d7-102">Перечисление CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="9a6d7-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="9a6d7-103">Предоставляет дополнительные сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a6d7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="9a6d7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9a6d7-105">Members</span></span>  
  
|<span data-ttu-id="9a6d7-106">Член</span><span class="sxs-lookup"><span data-stu-id="9a6d7-106">Member</span></span>|<span data-ttu-id="9a6d7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9a6d7-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="9a6d7-108">Исключение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="9a6d7-109">Исключение доступно для перехвата.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="9a6d7-110">Время исключения все еще может быть таким, что отладчик не сможет его перехватить.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="9a6d7-111">Например, если ниже текущего обратного вызова или события исключения, возникшего в результате JIT-вложения, нет никакого управляемого кода, такое исключение не может быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a6d7-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a6d7-112">Remarks</span></span>  
 <span data-ttu-id="9a6d7-113">В более поздних версиях для этого перечисления могут быть добавлены новые значения, поэтому следует подготовить код, использующий `CorDebugExceptionFlags` для неожиданных значений.</span><span class="sxs-lookup"><span data-stu-id="9a6d7-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6d7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9a6d7-114">Requirements</span></span>  
 <span data-ttu-id="9a6d7-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6d7-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a6d7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a6d7-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a6d7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a6d7-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6d7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9a6d7-119">See Also</span></span>  
 [<span data-ttu-id="9a6d7-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="9a6d7-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
