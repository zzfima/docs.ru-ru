---
title: Интерфейс ICLRDebugging
ms.date: 03/30/2017
api_name:
- ICLRDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging
helpviewer_keywords:
- ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6edee34c8560c989040475fee4a35c6bd2ddb3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155718"
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="ecea3-102">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="ecea3-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="ecea3-103">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="ecea3-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecea3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ecea3-104">Methods</span></span>  
  
|<span data-ttu-id="ecea3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ecea3-105">Method</span></span>|<span data-ttu-id="ecea3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ecea3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ecea3-107">Метод OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="ecea3-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="ecea3-108">Получает интерфейс «ICorDebugProcess», который соответствует общий язык среды выполнения (CLR) модуль загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="ecea3-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="ecea3-109">Метод CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="ecea3-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="ecea3-110">Определяет, является ли библиотеку, предоставленным [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейс по-прежнему используется, или может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="ecea3-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecea3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecea3-111">Remarks</span></span>  
 <span data-ttu-id="ecea3-112">Можно получить экземпляр `ICLRDebugging` интерфейса с помощью [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="ecea3-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecea3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ecea3-113">Requirements</span></span>  
 <span data-ttu-id="ecea3-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecea3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecea3-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecea3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecea3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecea3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecea3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecea3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecea3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ecea3-118">See also</span></span>

- [<span data-ttu-id="ecea3-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ecea3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ecea3-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="ecea3-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
