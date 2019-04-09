---
title: Интерфейс ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26efb3e43642b6d1fd10b084c2b321609c89d89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146514"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="3ca4c-102">Интерфейс ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="3ca4c-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="3ca4c-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="3ca4c-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ca4c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3ca4c-104">Methods</span></span>  
  
|<span data-ttu-id="3ca4c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3ca4c-105">Method</span></span>|<span data-ttu-id="3ca4c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3ca4c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ca4c-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="3ca4c-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-next-method.md)|<span data-ttu-id="3ca4c-108">Возвращает заданное число `ICorDebugModule` экземпляров из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="3ca4c-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ca4c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ca4c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ca4c-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3ca4c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca4c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3ca4c-111">Requirements</span></span>  
 <span data-ttu-id="3ca4c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca4c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca4c-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ca4c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ca4c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca4c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3ca4c-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3ca4c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ca4c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3ca4c-116">See also</span></span>

- [<span data-ttu-id="3ca4c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3ca4c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
