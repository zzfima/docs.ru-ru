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
ms.openlocfilehash: dd31bf458dde043a04e24251cedcac585fd385f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793041"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="754fd-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="754fd-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="754fd-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="754fd-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="754fd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="754fd-104">Methods</span></span>  
  
|<span data-ttu-id="754fd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="754fd-105">Method</span></span>|<span data-ttu-id="754fd-106">Описание</span><span class="sxs-lookup"><span data-stu-id="754fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="754fd-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="754fd-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="754fd-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="754fd-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="754fd-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="754fd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="754fd-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="754fd-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754fd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="754fd-111">Requirements</span></span>  
 <span data-ttu-id="754fd-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="754fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754fd-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="754fd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="754fd-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="754fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="754fd-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754fd-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="754fd-116">See also</span></span>

- [<span data-ttu-id="754fd-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="754fd-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="754fd-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="754fd-118">Debugging</span></span>](index.md)
