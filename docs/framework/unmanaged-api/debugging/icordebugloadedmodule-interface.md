---
title: "Интерфейс ICorDebugLoadedModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5cdc89ec81d76a3ce7d39a53e097745d6c9822f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="02337-102">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="02337-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="02337-103">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="02337-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02337-104">Методы</span><span class="sxs-lookup"><span data-stu-id="02337-104">Methods</span></span>  
  
|<span data-ttu-id="02337-105">Метод</span><span class="sxs-lookup"><span data-stu-id="02337-105">Method</span></span>|<span data-ttu-id="02337-106">Описание</span><span class="sxs-lookup"><span data-stu-id="02337-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02337-107">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="02337-107">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="02337-108">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="02337-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="02337-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="02337-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|<span data-ttu-id="02337-110">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="02337-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="02337-111">GetSize-метод</span><span class="sxs-lookup"><span data-stu-id="02337-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="02337-112">Возвращает размер загруженного модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="02337-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02337-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="02337-113">Remarks</span></span>  
 <span data-ttu-id="02337-114">Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.</span><span class="sxs-lookup"><span data-stu-id="02337-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02337-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="02337-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="02337-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="02337-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02337-117">Требования</span><span class="sxs-lookup"><span data-stu-id="02337-117">Requirements</span></span>  
 <span data-ttu-id="02337-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02337-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02337-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02337-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02337-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02337-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02337-121">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02337-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02337-122">См. также</span><span class="sxs-lookup"><span data-stu-id="02337-122">See Also</span></span>  
 [<span data-ttu-id="02337-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="02337-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="02337-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="02337-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
