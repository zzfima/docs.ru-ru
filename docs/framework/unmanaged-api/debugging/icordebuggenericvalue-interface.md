---
title: Интерфейс1 ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce4c1b73ab806958627bb68bfdcfcae890bc5e67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709836"
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="af3c3-102">Интерфейс1 ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="af3c3-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="af3c3-103">Подкласс «ICorDebugValue», которая применяется ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="af3c3-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="af3c3-104">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="af3c3-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af3c3-105">Методы</span><span class="sxs-lookup"><span data-stu-id="af3c3-105">Methods</span></span>  
  
|<span data-ttu-id="af3c3-106">Метод</span><span class="sxs-lookup"><span data-stu-id="af3c3-106">Method</span></span>|<span data-ttu-id="af3c3-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="af3c3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af3c3-108">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="af3c3-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="af3c3-109">Копирует значение в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="af3c3-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="af3c3-110">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="af3c3-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="af3c3-111">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="af3c3-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af3c3-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="af3c3-112">Remarks</span></span>  
 <span data-ttu-id="af3c3-113">`ICorDebugGenericValue` — Это интерфейс, так как это не поддерживающее удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="af3c3-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="af3c3-114">Для ссылочных типов значение является ссылкой, а не ссылки на содержимое.</span><span class="sxs-lookup"><span data-stu-id="af3c3-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="af3c3-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="af3c3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af3c3-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="af3c3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3c3-117">Требования</span><span class="sxs-lookup"><span data-stu-id="af3c3-117">Requirements</span></span>  
 <span data-ttu-id="af3c3-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af3c3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af3c3-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af3c3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af3c3-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af3c3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af3c3-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af3c3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3c3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="af3c3-122">See also</span></span>

- [<span data-ttu-id="af3c3-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="af3c3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
