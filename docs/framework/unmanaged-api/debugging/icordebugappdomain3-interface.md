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
ms.openlocfilehash: c3676cb32ceaf6f241672751f0feafbd3cb83e05
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968875"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="43a28-102">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="43a28-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="43a28-103">Предоставляет методы для получения сведений об управляемых представлениях среда выполнения Windows типов, которые в настоящее время загружены в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="43a28-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="43a28-104">Этот интерфейс является расширением интерфейсов ICorDebugAppDomain и ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="43a28-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43a28-105">Методы</span><span class="sxs-lookup"><span data-stu-id="43a28-105">Methods</span></span>  
  
|<span data-ttu-id="43a28-106">Метод</span><span class="sxs-lookup"><span data-stu-id="43a28-106">Method</span></span>|<span data-ttu-id="43a28-107">Описание</span><span class="sxs-lookup"><span data-stu-id="43a28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43a28-108">ICorDebugAppDomain3:: GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="43a28-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="43a28-109">Возвращает перечислитель для всех кэшированных среда выполнения Windowsных типов.</span><span class="sxs-lookup"><span data-stu-id="43a28-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="43a28-110">ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="43a28-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="43a28-111">Возвращает перечислитель для кэшированных среда выполнения Windowsных типов в домене приложения на основе их идентификаторов интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="43a28-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43a28-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="43a28-112">Remarks</span></span>  
 <span data-ttu-id="43a28-113">Этот интерфейс предназначен для использования отладчиком в сочетании с вызовом `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`вычисления функции.</span><span class="sxs-lookup"><span data-stu-id="43a28-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="43a28-114">Когда метод получает идентификаторы интерфейса, поддерживаемые объектом среда выполнения Windows Server, отладчик может использовать методы, определенные в этом интерфейсе, чтобы сопоставлять их с управляемыми типами, которые соответствуют этим интерфейсам.</span><span class="sxs-lookup"><span data-stu-id="43a28-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="43a28-115">Чтобы получить экземпляр этого интерфейса, выполните `QueryInterface` команду на экземпляре интерфейса ICorDebugAppDomain или ICorDebugAppDomain2.</span><span class="sxs-lookup"><span data-stu-id="43a28-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43a28-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="43a28-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a28-117">Требования</span><span class="sxs-lookup"><span data-stu-id="43a28-117">Requirements</span></span>  
 <span data-ttu-id="43a28-118">**Платформ** Среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="43a28-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="43a28-119">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="43a28-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a28-120">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="43a28-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a28-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a28-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a28-122">См. также</span><span class="sxs-lookup"><span data-stu-id="43a28-122">See also</span></span>

- [<span data-ttu-id="43a28-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="43a28-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
