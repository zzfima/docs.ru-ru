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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750609"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="a363e-102">Интерфейс ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="a363e-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="a363e-103">Представляет универсальный класс или класс параметром метода типа <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="a363e-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="a363e-104">Этот интерфейс расширяет [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a363e-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a363e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a363e-105">Methods</span></span>  
  
|<span data-ttu-id="a363e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a363e-106">Method</span></span>|<span data-ttu-id="a363e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a363e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a363e-108">Метод GetParameterizedType</span><span class="sxs-lookup"><span data-stu-id="a363e-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="a363e-109">Получает объявление типа для этого класса.</span><span class="sxs-lookup"><span data-stu-id="a363e-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="a363e-110">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="a363e-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="a363e-111">Для каждого метода этого класса задает значение, указывающее, является ли метод определяемого пользователем кода.</span><span class="sxs-lookup"><span data-stu-id="a363e-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a363e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a363e-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a363e-113">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a363e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a363e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a363e-114">Requirements</span></span>  
 <span data-ttu-id="a363e-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a363e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a363e-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a363e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a363e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a363e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a363e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a363e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a363e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a363e-119">See also</span></span>

- [<span data-ttu-id="a363e-120">Интерфейс ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="a363e-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="a363e-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a363e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
