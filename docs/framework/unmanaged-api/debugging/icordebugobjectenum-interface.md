---
title: Интерфейс ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452216a2ba4e8013d107977d82eae1508b2aba78
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967767"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="0a614-102">Интерфейс ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="0a614-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="0a614-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="0a614-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a614-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0a614-104">Methods</span></span>  
  
|<span data-ttu-id="0a614-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0a614-105">Method</span></span>|<span data-ttu-id="0a614-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0a614-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a614-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0a614-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="0a614-108">Получает RVA заданного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="0a614-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a614-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a614-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a614-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0a614-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a614-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0a614-111">Requirements</span></span>  
 <span data-ttu-id="0a614-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a614-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a614-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a614-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a614-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a614-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a614-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a614-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a614-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a614-116">See also</span></span>
- [<span data-ttu-id="0a614-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0a614-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
