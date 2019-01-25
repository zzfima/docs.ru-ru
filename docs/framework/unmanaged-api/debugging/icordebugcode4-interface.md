---
title: Интерфейс ICorDebugCode4
ms.date: 03/30/2017
api_name:
- ICorDebugCode4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4
helpviewer_keywords:
- ICorDebugCode4 interface [.NET Framework debugging]
ms.assetid: a3fdf523-274a-449c-920b-9fcb0aed1d97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c38ce53ca1c02ead03ab9d1ff1e53cda772333f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739723"
---
# <a name="icordebugcode4-interface"></a><span data-ttu-id="b706d-102">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="b706d-102">ICorDebugCode4 Interface</span></span>
<span data-ttu-id="b706d-103">Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="b706d-103">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b706d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b706d-104">Methods</span></span>  
  
|<span data-ttu-id="b706d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b706d-105">Method</span></span>|<span data-ttu-id="b706d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b706d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b706d-107">Метод EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="b706d-107">EnumerateVariableHomes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md)|<span data-ttu-id="b706d-108">Получает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="b706d-108">Gets an enumerator to the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b706d-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b706d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b706d-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b706d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b706d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b706d-111">Requirements</span></span>  
 <span data-ttu-id="b706d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b706d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b706d-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b706d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b706d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b706d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b706d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b706d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b706d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b706d-116">See also</span></span>


- [<span data-ttu-id="b706d-117">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="b706d-117">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="b706d-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b706d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
