---
title: Интерфейс ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eecb135e034c3565e805ea776115579488b2a4d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210312"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="8fc02-102">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="8fc02-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="8fc02-103">Логически расширяет интерфейс ICorDebugAssembly для обеспечения поддержки контейнерных сборок и их вложенных сборок.</span><span class="sxs-lookup"><span data-stu-id="8fc02-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fc02-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8fc02-104">Methods</span></span>  
  
|<span data-ttu-id="8fc02-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8fc02-105">Method</span></span>|<span data-ttu-id="8fc02-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8fc02-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fc02-107">Метод EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="8fc02-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="8fc02-108">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="8fc02-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="8fc02-109">Метод GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="8fc02-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="8fc02-110">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="8fc02-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fc02-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="8fc02-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fc02-112">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8fc02-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="8fc02-113">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8fc02-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc02-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8fc02-114">Requirements</span></span>  
 <span data-ttu-id="8fc02-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc02-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc02-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fc02-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fc02-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fc02-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fc02-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc02-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc02-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8fc02-119">See also</span></span>

- [<span data-ttu-id="8fc02-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8fc02-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8fc02-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="8fc02-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
