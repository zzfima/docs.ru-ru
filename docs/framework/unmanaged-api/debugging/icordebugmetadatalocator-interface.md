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
ms.openlocfilehash: 4e9b9221aa2f5e048a94c225660ba2ac9214549c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108838"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="cfde2-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="cfde2-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="cfde2-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="cfde2-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfde2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cfde2-104">Methods</span></span>  
  
|<span data-ttu-id="cfde2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cfde2-105">Method</span></span>|<span data-ttu-id="cfde2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cfde2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfde2-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="cfde2-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="cfde2-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="cfde2-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfde2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfde2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfde2-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cfde2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfde2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="cfde2-111">Requirements</span></span>  
 <span data-ttu-id="cfde2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfde2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfde2-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfde2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfde2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfde2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfde2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfde2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfde2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cfde2-116">See also</span></span>

- [<span data-ttu-id="cfde2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cfde2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cfde2-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="cfde2-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
