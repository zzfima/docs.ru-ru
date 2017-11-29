---
title: "Интерфейс ICLRDebugging"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging
helpviewer_keywords: ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3e061b95faafeec3c3d233ab54f128a23c3264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="b603b-102">Интерфейс ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="b603b-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="b603b-103">Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.</span><span class="sxs-lookup"><span data-stu-id="b603b-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b603b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b603b-104">Methods</span></span>  
  
|<span data-ttu-id="b603b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b603b-105">Method</span></span>|<span data-ttu-id="b603b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b603b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b603b-107">Метод OpenVirtualProcess</span><span class="sxs-lookup"><span data-stu-id="b603b-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="b603b-108">Получает интерфейс «ICorDebugProcess», который соответствует общие модуля среды CLR (CLR) загружена в процессе.</span><span class="sxs-lookup"><span data-stu-id="b603b-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="b603b-109">Метод CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="b603b-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="b603b-110">Определяет, используется ли библиотека, предоставленный компанией [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейса по-прежнему используется или может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="b603b-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b603b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b603b-111">Remarks</span></span>  
 <span data-ttu-id="b603b-112">Можно получить экземпляр `ICLRDebugging` интерфейса с помощью [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="b603b-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b603b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b603b-113">Requirements</span></span>  
 <span data-ttu-id="b603b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b603b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b603b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b603b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b603b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b603b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b603b-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b603b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b603b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b603b-118">See Also</span></span>  
 [<span data-ttu-id="b603b-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b603b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b603b-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="b603b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
