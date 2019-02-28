---
title: Интерфейс ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cff85a77b113440c2274910cae8ef93419d1bc1b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965362"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="c3f53-102">Интерфейс ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="c3f53-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="c3f53-103">Подкласс ICorDebugHeapValue, применяемый к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="c3f53-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3f53-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c3f53-104">Methods</span></span>  
  
|<span data-ttu-id="c3f53-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c3f53-105">Method</span></span>|<span data-ttu-id="c3f53-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="c3f53-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3f53-107">Метод GetLength</span><span class="sxs-lookup"><span data-stu-id="c3f53-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="c3f53-108">Возвращает число символов в строке, который ссылается этот `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="c3f53-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="c3f53-109">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="c3f53-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="c3f53-110">Получает строку, на которое указывает данный `ICorDebugStringValue`.</span><span class="sxs-lookup"><span data-stu-id="c3f53-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3f53-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3f53-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3f53-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c3f53-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3f53-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c3f53-113">Requirements</span></span>  
 <span data-ttu-id="c3f53-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3f53-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3f53-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3f53-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3f53-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3f53-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3f53-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f53-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f53-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c3f53-118">See also</span></span>
- [<span data-ttu-id="c3f53-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c3f53-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
