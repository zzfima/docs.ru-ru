---
title: Интерфейс ICorDebugExceptionObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: fa154d0bb48f4ecd4fc6a50ce22fd13c592b7c40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782734"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="d4ae7-102">Интерфейс ICorDebugExceptionObjectValue</span><span class="sxs-lookup"><span data-stu-id="d4ae7-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="d4ae7-103">Расширяет интерфейс "ICorDebugObjectValue" для предоставления сведений о трассировке стека из управляемого объекта исключения.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4ae7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d4ae7-104">Methods</span></span>  
  
|<span data-ttu-id="d4ae7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d4ae7-105">Method</span></span>|<span data-ttu-id="d4ae7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d4ae7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4ae7-107">Метод EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="d4ae7-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="d4ae7-108">Возвращает перечислитель для стека вызовов, внедренного в объект исключения.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4ae7-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d4ae7-109">Remarks</span></span>  
 <span data-ttu-id="d4ae7-110">Вызов `QueryInterface` будет выполнен для управляемых объектов, производных от <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4ae7-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ae7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d4ae7-111">Requirements</span></span>  
 <span data-ttu-id="d4ae7-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4ae7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ae7-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4ae7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4ae7-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4ae7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4ae7-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ae7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ae7-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="d4ae7-116">See also</span></span>

- [<span data-ttu-id="d4ae7-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d4ae7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d4ae7-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="d4ae7-118">Debugging</span></span>](index.md)
