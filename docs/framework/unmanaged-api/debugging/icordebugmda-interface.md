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
ms.openlocfilehash: 4201fe23bf54388510088e21471edce91809e94c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129798"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="07fc4-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="07fc4-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="07fc4-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="07fc4-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07fc4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="07fc4-104">Methods</span></span>  
  
|<span data-ttu-id="07fc4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="07fc4-105">Method</span></span>|<span data-ttu-id="07fc4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="07fc4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07fc4-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="07fc4-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="07fc4-108">Возвращает строку, содержащую описание этого MDA.</span><span class="sxs-lookup"><span data-stu-id="07fc4-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="07fc4-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="07fc4-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="07fc4-110">Возвращает флаги, связанные с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="07fc4-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="07fc4-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="07fc4-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="07fc4-112">Возвращает строку, содержащую имя этого MDA.</span><span class="sxs-lookup"><span data-stu-id="07fc4-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="07fc4-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="07fc4-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="07fc4-114">Возвращает идентификатор потока операционной системы, в котором выполняется этот MDA.</span><span class="sxs-lookup"><span data-stu-id="07fc4-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="07fc4-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="07fc4-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="07fc4-116">Возвращает полный XML-поток, связанный с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="07fc4-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07fc4-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="07fc4-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07fc4-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="07fc4-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07fc4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="07fc4-119">Requirements</span></span>  
 <span data-ttu-id="07fc4-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07fc4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07fc4-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07fc4-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07fc4-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07fc4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07fc4-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07fc4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07fc4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="07fc4-124">See also</span></span>

- [<span data-ttu-id="07fc4-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="07fc4-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="07fc4-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="07fc4-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
