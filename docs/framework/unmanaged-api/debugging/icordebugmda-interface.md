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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098673"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="6a372-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="6a372-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="6a372-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="6a372-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a372-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6a372-104">Methods</span></span>  
  
|<span data-ttu-id="6a372-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6a372-105">Method</span></span>|<span data-ttu-id="6a372-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6a372-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a372-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="6a372-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="6a372-108">Получает строку, содержащую описание данный MDA.</span><span class="sxs-lookup"><span data-stu-id="6a372-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="6a372-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="6a372-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="6a372-110">Получает флаги, связанные с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="6a372-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="6a372-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="6a372-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="6a372-112">Получает строку, содержащую имя данный MDA.</span><span class="sxs-lookup"><span data-stu-id="6a372-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="6a372-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="6a372-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="6a372-114">Получает идентификатор потока операционной системы, на котором выполняется данный MDA.</span><span class="sxs-lookup"><span data-stu-id="6a372-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="6a372-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="6a372-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="6a372-116">Получает полный XML-потока, связанного с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="6a372-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a372-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a372-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a372-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6a372-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a372-119">Требования</span><span class="sxs-lookup"><span data-stu-id="6a372-119">Requirements</span></span>  
 <span data-ttu-id="6a372-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a372-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a372-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a372-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a372-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a372-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6a372-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6a372-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a372-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6a372-124">See also</span></span>

- [<span data-ttu-id="6a372-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6a372-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6a372-126">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="6a372-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
