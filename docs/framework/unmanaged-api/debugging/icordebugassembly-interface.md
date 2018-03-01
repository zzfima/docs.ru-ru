---
title: "ICorDebugAssembly интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6331c00c2be0805afb56028e9e1a13cd11168cf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="46671-102">ICorDebugAssembly интерфейс1</span><span class="sxs-lookup"><span data-stu-id="46671-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="46671-103">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="46671-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46671-104">Методы</span><span class="sxs-lookup"><span data-stu-id="46671-104">Methods</span></span>  
  
|<span data-ttu-id="46671-105">Метод</span><span class="sxs-lookup"><span data-stu-id="46671-105">Method</span></span>|<span data-ttu-id="46671-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="46671-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46671-107">Метод EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="46671-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="46671-108">Получает перечислитель для модулей, содержащиеся в сборке.</span><span class="sxs-lookup"><span data-stu-id="46671-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="46671-109">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="46671-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="46671-110">Получает указатель интерфейса на домен приложения, который содержит это `ICorDebugAssembly` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="46671-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="46671-111">Метод GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="46671-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="46671-112">Не реализован в текущей версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46671-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="46671-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="46671-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="46671-114">Возвращает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="46671-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="46671-115">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="46671-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="46671-116">Получает экземпляр ICorDebugProcess, в которой выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="46671-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46671-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="46671-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46671-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="46671-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46671-119">Требования</span><span class="sxs-lookup"><span data-stu-id="46671-119">Requirements</span></span>  
 <span data-ttu-id="46671-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46671-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46671-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="46671-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="46671-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46671-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46671-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46671-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46671-124">См. также</span><span class="sxs-lookup"><span data-stu-id="46671-124">See Also</span></span>  
 [<span data-ttu-id="46671-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="46671-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
