---
title: Интерфейс ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8f3a881a1beceb7d4aa35e2bd9a5e9e5419a391
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654871"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="f4b65-102">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="f4b65-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="f4b65-103">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="f4b65-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4b65-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f4b65-104">Methods</span></span>  
  
|<span data-ttu-id="f4b65-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f4b65-105">Method</span></span>|<span data-ttu-id="f4b65-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f4b65-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4b65-107">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="f4b65-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="f4b65-108">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="f4b65-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="f4b65-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="f4b65-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="f4b65-110">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="f4b65-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="f4b65-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="f4b65-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="f4b65-112">Возвращает размер загруженного модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="f4b65-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4b65-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4b65-113">Remarks</span></span>  
 <span data-ttu-id="f4b65-114">Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.</span><span class="sxs-lookup"><span data-stu-id="f4b65-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4b65-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f4b65-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f4b65-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f4b65-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4b65-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f4b65-117">Requirements</span></span>  
 <span data-ttu-id="f4b65-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4b65-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b65-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4b65-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4b65-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4b65-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4b65-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b65-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b65-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f4b65-122">See also</span></span>
- [<span data-ttu-id="f4b65-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f4b65-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f4b65-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="f4b65-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
