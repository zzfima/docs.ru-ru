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
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177532"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="c300a-102">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="c300a-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="c300a-103">Предоставляет методы для получения сведений об управляемых представлений [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов, в настоящий момент загружены в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="c300a-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="c300a-104">Этот интерфейс является расширением ICorDebugAppDomain и ICorDebugAppDomain2 интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="c300a-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c300a-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c300a-105">Methods</span></span>  
  
|<span data-ttu-id="c300a-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c300a-106">Method</span></span>|<span data-ttu-id="c300a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c300a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c300a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="c300a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="c300a-109">Получает перечислитель для всех кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов.</span><span class="sxs-lookup"><span data-stu-id="c300a-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="c300a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="c300a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="c300a-111">Получает перечислитель для кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов в домене приложения, по их идентификаторам интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c300a-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c300a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="c300a-112">Remarks</span></span>  
 <span data-ttu-id="c300a-113">Этот интерфейс предназначен для использования с помощью отладчика в сочетании с вызовом функции оценки `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span><span class="sxs-lookup"><span data-stu-id="c300a-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="c300a-114">Когда этот метод извлекает идентификаторы интерфейса, поддерживаемых [!INCLUDE[wrt](../../../../includes/wrt-md.md)] объекта сервера, отладчик может использовать методы, определенные в этом интерфейсе, чтобы сопоставить их с управляемых типов, которые соответствуют эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="c300a-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="c300a-115">Чтобы получить экземпляр этого интерфейса, выполните `QueryInterface` на экземпляр интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="c300a-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c300a-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c300a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c300a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c300a-117">Requirements</span></span>  
 **<span data-ttu-id="c300a-118">Платформы:</span><span class="sxs-lookup"><span data-stu-id="c300a-118">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="c300a-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c300a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c300a-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c300a-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c300a-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c300a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c300a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c300a-122">See also</span></span>

- [<span data-ttu-id="c300a-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c300a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
