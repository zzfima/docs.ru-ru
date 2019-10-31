---
title: Интерфейс ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: cb2ab28824d209dd1eed627600e30e9ddb0d7c7a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125725"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="8ff0f-102">Интерфейс ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="8ff0f-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="8ff0f-103">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="8ff0f-104">Этот интерфейс расширяет [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8ff0f-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ff0f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8ff0f-105">Methods</span></span>  
  
|<span data-ttu-id="8ff0f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8ff0f-106">Method</span></span>|<span data-ttu-id="8ff0f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8ff0f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ff0f-108">Метод GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="8ff0f-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="8ff0f-109">Возвращает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="8ff0f-110">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8ff0f-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="8ff0f-111">Для каждого метода этого класса задает значение, указывающее, является ли метод определяемым пользователем кодом.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ff0f-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="8ff0f-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ff0f-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8ff0f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ff0f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8ff0f-114">Requirements</span></span>  
 <span data-ttu-id="8ff0f-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff0f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff0f-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ff0f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ff0f-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff0f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff0f-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff0f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff0f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8ff0f-119">See also</span></span>

- [<span data-ttu-id="8ff0f-120">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="8ff0f-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="8ff0f-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8ff0f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
