---
title: "Интерфейс ICorDebugDataTarget2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2aefdb34277d2cb7ebc29ef817745b85064475d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="0a644-102">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="0a644-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="0a644-103">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0a644-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a644-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0a644-104">Methods</span></span>  
  
|<span data-ttu-id="0a644-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0a644-105">Method</span></span>|<span data-ttu-id="0a644-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="0a644-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a644-107">Метод CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="0a644-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="0a644-108">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="0a644-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="0a644-109">Метод EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0a644-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="0a644-110">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="0a644-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="0a644-111">Метод GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="0a644-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="0a644-112">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="0a644-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="0a644-113">Метод GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="0a644-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="0a644-114">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="0a644-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="0a644-115">Метод GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="0a644-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="0a644-116">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="0a644-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a644-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a644-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a644-118">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0a644-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0a644-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0a644-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a644-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0a644-120">Requirements</span></span>  
 <span data-ttu-id="0a644-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a644-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a644-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a644-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a644-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a644-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a644-124">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a644-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a644-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0a644-125">See Also</span></span>  
 [<span data-ttu-id="0a644-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0a644-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0a644-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="0a644-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
