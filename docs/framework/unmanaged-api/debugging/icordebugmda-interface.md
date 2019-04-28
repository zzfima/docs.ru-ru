---
title: Интерфейс ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916673"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="7c6f5-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="7c6f5-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="7c6f5-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="7c6f5-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c6f5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7c6f5-104">Methods</span></span>  
  
|<span data-ttu-id="7c6f5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7c6f5-105">Method</span></span>|<span data-ttu-id="7c6f5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7c6f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c6f5-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="7c6f5-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="7c6f5-108">Получает строку, содержащую описание данный MDA.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="7c6f5-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="7c6f5-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="7c6f5-110">Получает флаги, связанные с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="7c6f5-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="7c6f5-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="7c6f5-112">Получает строку, содержащую имя данный MDA.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="7c6f5-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="7c6f5-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="7c6f5-114">Получает идентификатор потока операционной системы, на котором выполняется данный MDA.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="7c6f5-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="7c6f5-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="7c6f5-116">Получает полный XML-потока, связанного с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c6f5-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c6f5-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c6f5-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7c6f5-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6f5-119">Требования</span><span class="sxs-lookup"><span data-stu-id="7c6f5-119">Requirements</span></span>  
 <span data-ttu-id="7c6f5-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c6f5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6f5-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c6f5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c6f5-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c6f5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c6f5-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6f5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c6f5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7c6f5-124">See also</span></span>

- [<span data-ttu-id="7c6f5-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7c6f5-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7c6f5-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="7c6f5-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
