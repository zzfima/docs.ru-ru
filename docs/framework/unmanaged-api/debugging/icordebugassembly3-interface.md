---
title: Интерфейс ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca77360c36ff2cdce7ee47d5c3883dd824c6cef8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959325"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="fd0e3-102">Интерфейс ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="fd0e3-102">ICorDebugAssembly3 Interface</span></span>
<span data-ttu-id="fd0e3-103">Логически расширяет интерфейс ICorDebugAssembly, чтобы обеспечить поддержку для сборок контейнеров и содержащихся в них сборок.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd0e3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fd0e3-104">Methods</span></span>  
  
|<span data-ttu-id="fd0e3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fd0e3-105">Method</span></span>|<span data-ttu-id="fd0e3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fd0e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd0e3-107">Метод EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="fd0e3-107">EnumerateContainedAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="fd0e3-108">Получает перечислитель для сборок, содержащихся в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="fd0e3-109">Метод GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="fd0e3-109">GetContainerAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="fd0e3-110">Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0e3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd0e3-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd0e3-112">Этот интерфейс доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="fd0e3-113">Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fd0e3-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0e3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fd0e3-114">Requirements</span></span>  
 <span data-ttu-id="fd0e3-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0e3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0e3-116">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="fd0e3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd0e3-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="fd0e3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd0e3-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0e3-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0e3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fd0e3-119">See also</span></span>

- [<span data-ttu-id="fd0e3-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fd0e3-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fd0e3-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="fd0e3-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
