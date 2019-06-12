---
title: Интерфейс ICorDebugAppDomain3
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025893"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="65b8f-102">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="65b8f-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="65b8f-103">Предоставляет методы для получения сведений об управляемых представления типов среды выполнения Windows, загруженные в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="65b8f-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="65b8f-104">Этот интерфейс является расширением ICorDebugAppDomain и ICorDebugAppDomain2 интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="65b8f-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65b8f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="65b8f-105">Methods</span></span>  
  
|<span data-ttu-id="65b8f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="65b8f-106">Method</span></span>|<span data-ttu-id="65b8f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="65b8f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65b8f-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="65b8f-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="65b8f-109">Получает перечислитель для всех кэшированных типов среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="65b8f-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="65b8f-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="65b8f-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="65b8f-111">Возвращает перечислитель для кэшированных типов среды выполнения Windows в домене приложения, на основе их идентификаторов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="65b8f-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65b8f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="65b8f-112">Remarks</span></span>  
 <span data-ttu-id="65b8f-113">Этот интерфейс предназначен для использования с помощью отладчика в сочетании с вызовом функции оценки `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="65b8f-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="65b8f-114">Когда этот метод извлекает идентификаторы интерфейса, поддерживаемого объектом среды выполнения Windows server, отладчик может использовать методы, определенные в этом интерфейсе для сопоставления их с управляемых типов, которые соответствуют эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="65b8f-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="65b8f-115">Чтобы получить экземпляр этого интерфейса, выполните `QueryInterface` на экземпляр интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="65b8f-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b8f-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="65b8f-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b8f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="65b8f-117">Requirements</span></span>  
 <span data-ttu-id="65b8f-118">**Платформы:** Среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="65b8f-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="65b8f-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65b8f-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65b8f-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65b8f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65b8f-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b8f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b8f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="65b8f-122">See also</span></span>

- [<span data-ttu-id="65b8f-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="65b8f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
