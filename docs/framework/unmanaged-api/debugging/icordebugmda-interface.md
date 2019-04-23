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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098673"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="16813-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="16813-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="16813-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="16813-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16813-104">Методы</span><span class="sxs-lookup"><span data-stu-id="16813-104">Methods</span></span>  
  
|<span data-ttu-id="16813-105">Метод</span><span class="sxs-lookup"><span data-stu-id="16813-105">Method</span></span>|<span data-ttu-id="16813-106">Описание</span><span class="sxs-lookup"><span data-stu-id="16813-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16813-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="16813-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="16813-108">Получает строку, содержащую описание данный MDA.</span><span class="sxs-lookup"><span data-stu-id="16813-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="16813-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="16813-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="16813-110">Получает флаги, связанные с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="16813-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="16813-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="16813-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="16813-112">Получает строку, содержащую имя данный MDA.</span><span class="sxs-lookup"><span data-stu-id="16813-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="16813-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="16813-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="16813-114">Получает идентификатор потока операционной системы, на котором выполняется данный MDA.</span><span class="sxs-lookup"><span data-stu-id="16813-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="16813-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="16813-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="16813-116">Получает полный XML-потока, связанного с данный MDA.</span><span class="sxs-lookup"><span data-stu-id="16813-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16813-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="16813-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16813-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="16813-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16813-119">Требования</span><span class="sxs-lookup"><span data-stu-id="16813-119">Requirements</span></span>  
 <span data-ttu-id="16813-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16813-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16813-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16813-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16813-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16813-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16813-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16813-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16813-124">См. также</span><span class="sxs-lookup"><span data-stu-id="16813-124">See also</span></span>

- [<span data-ttu-id="16813-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="16813-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="16813-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="16813-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
