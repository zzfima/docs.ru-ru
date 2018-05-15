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
ms.openlocfilehash: 550b39445dfe4d97e712e9a4c73aa0f497b3fce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="94e4f-102">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="94e4f-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="94e4f-103">Представляет сообщение управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="94e4f-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94e4f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="94e4f-104">Methods</span></span>  
  
|<span data-ttu-id="94e4f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="94e4f-105">Method</span></span>|<span data-ttu-id="94e4f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="94e4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94e4f-107">Метод GetDescription</span><span class="sxs-lookup"><span data-stu-id="94e4f-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="94e4f-108">Возвращает строку, содержащую описание данный MDA.</span><span class="sxs-lookup"><span data-stu-id="94e4f-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="94e4f-109">Метод GetFlags</span><span class="sxs-lookup"><span data-stu-id="94e4f-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="94e4f-110">Получает флаги, связанные с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="94e4f-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="94e4f-111">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="94e4f-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="94e4f-112">Возвращает строку, содержащую имя данного MDA.</span><span class="sxs-lookup"><span data-stu-id="94e4f-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="94e4f-113">Метод GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="94e4f-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="94e4f-114">Получает идентификатор потока операционной системы, на котором выполняется данный MDA.</span><span class="sxs-lookup"><span data-stu-id="94e4f-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="94e4f-115">Метод GetXML</span><span class="sxs-lookup"><span data-stu-id="94e4f-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="94e4f-116">Получает полный XML-поток, связанный с этим MDA.</span><span class="sxs-lookup"><span data-stu-id="94e4f-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e4f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="94e4f-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94e4f-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="94e4f-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e4f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="94e4f-119">Requirements</span></span>  
 <span data-ttu-id="94e4f-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94e4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e4f-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94e4f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94e4f-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94e4f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94e4f-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e4f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="94e4f-124">See Also</span></span>  
 [<span data-ttu-id="94e4f-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="94e4f-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="94e4f-126">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="94e4f-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
