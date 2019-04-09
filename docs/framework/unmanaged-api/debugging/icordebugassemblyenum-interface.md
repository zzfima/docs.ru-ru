---
title: Интерфейс ICorDebugAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fef4d757cf528cd3dc7d79db04d33c2cad9bbf1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189849"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="58a43-102">Интерфейс ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="58a43-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="58a43-103">Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="58a43-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="58a43-104">Методы</span><span class="sxs-lookup"><span data-stu-id="58a43-104">Methods</span></span>  
  
|<span data-ttu-id="58a43-105">Метод</span><span class="sxs-lookup"><span data-stu-id="58a43-105">Method</span></span>|<span data-ttu-id="58a43-106">Описание</span><span class="sxs-lookup"><span data-stu-id="58a43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="58a43-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="58a43-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-next-method.md)|<span data-ttu-id="58a43-108">Возвращает заданное число `ICorDebugAssembly` экземпляров в перечислении, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="58a43-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58a43-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="58a43-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58a43-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="58a43-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a43-111">Требования</span><span class="sxs-lookup"><span data-stu-id="58a43-111">Requirements</span></span>  
 <span data-ttu-id="58a43-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58a43-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58a43-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58a43-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58a43-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58a43-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="58a43-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="58a43-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58a43-116">См. также</span><span class="sxs-lookup"><span data-stu-id="58a43-116">See also</span></span>

- [<span data-ttu-id="58a43-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="58a43-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
