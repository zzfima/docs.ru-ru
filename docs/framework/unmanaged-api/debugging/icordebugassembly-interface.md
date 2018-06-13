---
title: ICorDebugAssembly интерфейс1
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88134fb7854091bb60e8084a6d776bdec922c7e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406374"
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="f9a93-102">ICorDebugAssembly интерфейс1</span><span class="sxs-lookup"><span data-stu-id="f9a93-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="f9a93-103">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="f9a93-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9a93-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f9a93-104">Methods</span></span>  
  
|<span data-ttu-id="f9a93-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f9a93-105">Method</span></span>|<span data-ttu-id="f9a93-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f9a93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9a93-107">Метод EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="f9a93-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="f9a93-108">Получает перечислитель для модулей, содержащиеся в сборке.</span><span class="sxs-lookup"><span data-stu-id="f9a93-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="f9a93-109">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="f9a93-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="f9a93-110">Получает указатель интерфейса на домен приложения, который содержит это `ICorDebugAssembly` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f9a93-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="f9a93-111">Метод GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="f9a93-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="f9a93-112">Не реализован в текущей версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f9a93-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="f9a93-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="f9a93-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="f9a93-114">Возвращает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="f9a93-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="f9a93-115">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="f9a93-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="f9a93-116">Получает экземпляр ICorDebugProcess, в которой выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="f9a93-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9a93-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9a93-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9a93-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="f9a93-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9a93-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f9a93-119">Requirements</span></span>  
 <span data-ttu-id="f9a93-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9a93-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9a93-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9a93-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9a93-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9a93-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9a93-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9a93-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9a93-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f9a93-124">See Also</span></span>  
 [<span data-ttu-id="f9a93-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f9a93-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
