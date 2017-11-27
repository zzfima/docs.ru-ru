---
title: "Интерфейс ICorDebugMetaDataLocator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMetaDataLocator
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMetaDataLocator
helpviewer_keywords: ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4611581bd2692d7c2be48adad1db3c495080e776
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="3e14a-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="3e14a-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="3e14a-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="3e14a-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3e14a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3e14a-104">Methods</span></span>  
  
|<span data-ttu-id="3e14a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3e14a-105">Method</span></span>|<span data-ttu-id="3e14a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3e14a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3e14a-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="3e14a-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="3e14a-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="3e14a-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e14a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e14a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e14a-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3e14a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e14a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3e14a-111">Requirements</span></span>  
 <span data-ttu-id="3e14a-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e14a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e14a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e14a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e14a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e14a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e14a-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e14a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e14a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3e14a-116">See Also</span></span>  
 [<span data-ttu-id="3e14a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3e14a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="3e14a-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="3e14a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
