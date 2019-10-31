---
title: Интерфейс ICorDebugAssembly
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
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133973"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="e589d-102">Интерфейс ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="e589d-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="e589d-103">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="e589d-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e589d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e589d-104">Methods</span></span>  
  
|<span data-ttu-id="e589d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e589d-105">Method</span></span>|<span data-ttu-id="e589d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e589d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e589d-107">Метод EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="e589d-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="e589d-108">Возвращает перечислитель для модулей, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="e589d-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="e589d-109">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="e589d-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="e589d-110">Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e589d-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="e589d-111">Метод GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="e589d-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="e589d-112">Не реализовано в текущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e589d-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="e589d-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="e589d-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="e589d-114">Возвращает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="e589d-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="e589d-115">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="e589d-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="e589d-116">Возвращает экземпляр ICorDebugProcess, в котором выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="e589d-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e589d-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="e589d-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e589d-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e589d-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e589d-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e589d-119">Requirements</span></span>  
 <span data-ttu-id="e589d-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e589d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e589d-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e589d-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e589d-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e589d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e589d-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e589d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e589d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e589d-124">See also</span></span>

- [<span data-ttu-id="e589d-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e589d-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
