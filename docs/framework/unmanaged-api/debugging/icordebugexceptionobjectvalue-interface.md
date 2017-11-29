---
title: "Интерфейс ICorDebugExceptionObjectValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue
helpviewer_keywords: ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 47733a6af18d42d0d9db1e50cf21646289ef1443
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="31df9-102">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="31df9-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="31df9-103">Расширяет интерфейс «ICorDebugObjectValue» для предоставления сведений трассировки стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="31df9-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31df9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="31df9-104">Methods</span></span>  
  
|<span data-ttu-id="31df9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="31df9-105">Method</span></span>|<span data-ttu-id="31df9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="31df9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31df9-107">Метод EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="31df9-107">EnumerateExceptionCallStack Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="31df9-108">Получает перечислитель для стека вызовов, встроенных в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="31df9-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31df9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="31df9-109">Remarks</span></span>  
 <span data-ttu-id="31df9-110">Вызов `QueryInterface` проходит успешно для управляемых объектов, которые являются производными от <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31df9-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31df9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="31df9-111">Requirements</span></span>  
 <span data-ttu-id="31df9-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31df9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31df9-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31df9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31df9-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31df9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31df9-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31df9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31df9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="31df9-116">See Also</span></span>  
 [<span data-ttu-id="31df9-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="31df9-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="31df9-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="31df9-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 
