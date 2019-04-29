---
title: Интерфейс ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e91dda9cbc5957768e98db2b2a9e1026d94c03e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946297"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="93871-102">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="93871-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="93871-103">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="93871-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93871-104">Методы</span><span class="sxs-lookup"><span data-stu-id="93871-104">Methods</span></span>  
  
|<span data-ttu-id="93871-105">Метод</span><span class="sxs-lookup"><span data-stu-id="93871-105">Method</span></span>|<span data-ttu-id="93871-106">Описание</span><span class="sxs-lookup"><span data-stu-id="93871-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93871-107">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="93871-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="93871-108">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="93871-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="93871-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="93871-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="93871-110">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="93871-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="93871-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="93871-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="93871-112">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="93871-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93871-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="93871-113">Remarks</span></span>  
 <span data-ttu-id="93871-114">Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.</span><span class="sxs-lookup"><span data-stu-id="93871-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93871-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="93871-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="93871-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="93871-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93871-117">Требования</span><span class="sxs-lookup"><span data-stu-id="93871-117">Requirements</span></span>  
 <span data-ttu-id="93871-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93871-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93871-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93871-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93871-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93871-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93871-121">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93871-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93871-122">См. также</span><span class="sxs-lookup"><span data-stu-id="93871-122">See also</span></span>

- [<span data-ttu-id="93871-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="93871-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="93871-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="93871-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
