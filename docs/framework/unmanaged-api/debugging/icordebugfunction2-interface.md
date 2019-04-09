---
title: Интерфейс ICorDebugFunction2
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 159cebc76f732629ed84a3b6c9041cc15f8bbb69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199379"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="8b7e1-102">Интерфейс ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="8b7e1-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="8b7e1-103">Логически расширяет интерфейс ICorDebugFunction для обеспечения поддержки Just My Code пошаговую отладку, который пропускает непользовательский код.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b7e1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8b7e1-104">Methods</span></span>  
  
|<span data-ttu-id="8b7e1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8b7e1-105">Method</span></span>|<span data-ttu-id="8b7e1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8b7e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b7e1-107">Метод EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="8b7e1-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="8b7e1-108">(Еще не реализовано). Получает указатель на интерфейс ICorDebugCodeEnum, содержащий инструкции машинного кода в функции, на которые ссылается этот объект ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="8b7e1-109">Метод GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8b7e1-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="8b7e1-110">Получает значение, указывающее, помечена ли эта функция как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="8b7e1-111">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="8b7e1-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="8b7e1-112">Получает версию "Изменить и продолжить" этой функции.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="8b7e1-113">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8b7e1-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="8b7e1-114">Помечает эту функцию только мой код пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b7e1-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b7e1-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b7e1-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8b7e1-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b7e1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8b7e1-117">Requirements</span></span>  
 <span data-ttu-id="8b7e1-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b7e1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b7e1-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b7e1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b7e1-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b7e1-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8b7e1-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8b7e1-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b7e1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8b7e1-122">See also</span></span>

- [<span data-ttu-id="8b7e1-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8b7e1-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
