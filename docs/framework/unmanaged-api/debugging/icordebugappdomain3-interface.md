---
title: "Интерфейс ICorDebugAppDomain3"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 017a2f018569b17c0b0011638e16f1921b6c9801
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="84993-102">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="84993-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="84993-103">Предоставляет методы для получения сведений об управляемом представления [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов, загруженные в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="84993-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="84993-104">Этот интерфейс является расширением ICorDebugAppDomain и ICorDebugAppDomain2 интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="84993-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84993-105">Методы</span><span class="sxs-lookup"><span data-stu-id="84993-105">Methods</span></span>  
  
|<span data-ttu-id="84993-106">Метод</span><span class="sxs-lookup"><span data-stu-id="84993-106">Method</span></span>|<span data-ttu-id="84993-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="84993-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84993-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="84993-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="84993-109">Возвращает перечислитель для всех кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов.</span><span class="sxs-lookup"><span data-stu-id="84993-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="84993-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="84993-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="84993-111">Возвращает перечислитель для кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов в домене приложения на основе их интерфейс идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="84993-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84993-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="84993-112">Remarks</span></span>  
 <span data-ttu-id="84993-113">Этот интерфейс предназначен для использования отладчика в сочетании с помощью вызова функции оценки для `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="84993-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="84993-114">Если этот метод извлекает идентификаторы интерфейса, поддерживаемых [!INCLUDE[wrt](../../../../includes/wrt-md.md)] объекта сервера, отладчик может использовать методы, определенные в этом интерфейсе, чтобы сопоставить их с управляемых типов, которые соответствуют эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="84993-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="84993-115">Чтобы получить экземпляр этого интерфейса, запустите `QueryInterface` на экземпляр интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="84993-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84993-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="84993-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84993-117">Требования</span><span class="sxs-lookup"><span data-stu-id="84993-117">Requirements</span></span>  
 <span data-ttu-id="84993-118">**Платформы:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84993-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="84993-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84993-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84993-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84993-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84993-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84993-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84993-122">См. также</span><span class="sxs-lookup"><span data-stu-id="84993-122">See Also</span></span>  
 [<span data-ttu-id="84993-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84993-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
