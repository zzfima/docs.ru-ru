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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 015085cff23028814937dfef9aea19af7438b4f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173814"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="6902d-102">Интерфейс ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="6902d-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="6902d-103">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="6902d-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="6902d-104">Этот интерфейс расширяет [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6902d-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6902d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6902d-105">Methods</span></span>  
  
|<span data-ttu-id="6902d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="6902d-106">Method</span></span>|<span data-ttu-id="6902d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6902d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6902d-108">Метод GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="6902d-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="6902d-109">Получает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="6902d-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="6902d-110">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="6902d-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="6902d-111">Для каждого метода этого класса задает значение, указывающее, является ли метод определяемого пользователем кода.</span><span class="sxs-lookup"><span data-stu-id="6902d-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6902d-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6902d-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6902d-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6902d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6902d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6902d-114">Requirements</span></span>  
 <span data-ttu-id="6902d-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6902d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6902d-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6902d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6902d-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6902d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6902d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6902d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6902d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6902d-119">See also</span></span>

- [<span data-ttu-id="6902d-120">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="6902d-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="6902d-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6902d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
