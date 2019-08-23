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
ms.openlocfilehash: 5a4349ad4dbaeafa63689ef85a307211428f8538
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917088"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="8314b-102">Интерфейс ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="8314b-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="8314b-103">Логически расширяет интерфейс ICorDebugFunction, чтобы обеспечить поддержку Только мой код пошаговой отладке, которая пропускает код, не являющийся пользовательским.</span><span class="sxs-lookup"><span data-stu-id="8314b-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8314b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8314b-104">Methods</span></span>  
  
|<span data-ttu-id="8314b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8314b-105">Method</span></span>|<span data-ttu-id="8314b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8314b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8314b-107">Метод EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="8314b-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="8314b-108">(Еще не реализовано.) Возвращает указатель интерфейса на Икордебугкодинум, содержащий операторы машинного кода в функции, на которую ссылается этот объект ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="8314b-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="8314b-109">Метод GetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8314b-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="8314b-110">Возвращает значение, указывающее, помечена ли эта функция как пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="8314b-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="8314b-111">Метод GetVersionNumber</span><span class="sxs-lookup"><span data-stu-id="8314b-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="8314b-112">Возвращает версию функции "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="8314b-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="8314b-113">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="8314b-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="8314b-114">Помечает эту функцию для Только мой код пошагового выполнения.</span><span class="sxs-lookup"><span data-stu-id="8314b-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8314b-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="8314b-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8314b-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8314b-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8314b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="8314b-117">Requirements</span></span>  
 <span data-ttu-id="8314b-118">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8314b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8314b-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8314b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8314b-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="8314b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8314b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8314b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8314b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8314b-122">See also</span></span>

- [<span data-ttu-id="8314b-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8314b-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
