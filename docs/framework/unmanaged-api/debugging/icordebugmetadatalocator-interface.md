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
ms.openlocfilehash: 1116945ae1a886f1b9491e0baf183e20c4fff177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136616"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="b6c2a-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="b6c2a-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="b6c2a-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6c2a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b6c2a-104">Methods</span></span>  
  
|<span data-ttu-id="b6c2a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b6c2a-105">Method</span></span>|<span data-ttu-id="b6c2a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b6c2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6c2a-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="b6c2a-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="b6c2a-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6c2a-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b6c2a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6c2a-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c2a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b6c2a-111">Requirements</span></span>  
 <span data-ttu-id="b6c2a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c2a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c2a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6c2a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6c2a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6c2a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6c2a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c2a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b6c2a-116">See also</span></span>

- [<span data-ttu-id="b6c2a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b6c2a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b6c2a-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="b6c2a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
