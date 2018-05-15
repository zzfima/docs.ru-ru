---
title: Интерфейс ICorDebugMetaDataLocator
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1673b6045a6344ee0eeadf4ec3003206f92cde4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="d99e1-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="d99e1-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="d99e1-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="d99e1-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d99e1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d99e1-104">Methods</span></span>  
  
|<span data-ttu-id="d99e1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d99e1-105">Method</span></span>|<span data-ttu-id="d99e1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d99e1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d99e1-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="d99e1-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="d99e1-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="d99e1-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d99e1-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d99e1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d99e1-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d99e1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d99e1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d99e1-111">Requirements</span></span>  
 <span data-ttu-id="d99e1-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d99e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d99e1-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d99e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d99e1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d99e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d99e1-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d99e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99e1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d99e1-116">See Also</span></span>  
 [<span data-ttu-id="d99e1-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d99e1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d99e1-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="d99e1-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
