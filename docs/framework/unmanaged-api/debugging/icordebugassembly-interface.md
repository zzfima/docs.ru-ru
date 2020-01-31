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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784678"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="64831-102">Интерфейс ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="64831-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="64831-103">Представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="64831-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64831-104">Методы</span><span class="sxs-lookup"><span data-stu-id="64831-104">Methods</span></span>  
  
|<span data-ttu-id="64831-105">Метод</span><span class="sxs-lookup"><span data-stu-id="64831-105">Method</span></span>|<span data-ttu-id="64831-106">Описание</span><span class="sxs-lookup"><span data-stu-id="64831-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64831-107">Метод EnumerateModules</span><span class="sxs-lookup"><span data-stu-id="64831-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="64831-108">Возвращает перечислитель для модулей, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="64831-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="64831-109">Метод GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="64831-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="64831-110">Возвращает указатель интерфейса на домен приложения, содержащий данный `ICorDebugAssembly` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="64831-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="64831-111">Метод GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="64831-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="64831-112">Не реализовано в текущей версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64831-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="64831-113">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="64831-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="64831-114">Возвращает имя сборки.</span><span class="sxs-lookup"><span data-stu-id="64831-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="64831-115">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="64831-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="64831-116">Возвращает экземпляр ICorDebugProcess, в котором выполняется сборка.</span><span class="sxs-lookup"><span data-stu-id="64831-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64831-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="64831-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64831-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="64831-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64831-119">Требования</span><span class="sxs-lookup"><span data-stu-id="64831-119">Requirements</span></span>  
 <span data-ttu-id="64831-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64831-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64831-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64831-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64831-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64831-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64831-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64831-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64831-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="64831-124">See also</span></span>

- [<span data-ttu-id="64831-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64831-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
