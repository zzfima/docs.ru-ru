---
title: Интерфейс ICorDebugDataTarget2
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85ff64e30519e448b87c2e9ae5d2c66959d836fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412137"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="19820-102">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="19820-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="19820-103">Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)интерфейса.</span><span class="sxs-lookup"><span data-stu-id="19820-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19820-104">Методы</span><span class="sxs-lookup"><span data-stu-id="19820-104">Methods</span></span>  
  
|<span data-ttu-id="19820-105">Метод</span><span class="sxs-lookup"><span data-stu-id="19820-105">Method</span></span>|<span data-ttu-id="19820-106">Описание</span><span class="sxs-lookup"><span data-stu-id="19820-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19820-107">Метод CreateVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="19820-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="19820-108">Создает новый элемент очистки стека, запускающий операцию очистки, начиная с исходного контекста (который не обязательно является концом потока).</span><span class="sxs-lookup"><span data-stu-id="19820-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="19820-109">Метод EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="19820-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="19820-110">Возвращает список идентификаторов активных потоков.</span><span class="sxs-lookup"><span data-stu-id="19820-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="19820-111">Метод GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="19820-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="19820-112">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="19820-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="19820-113">Метод GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="19820-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="19820-114">Возвращает путь для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="19820-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="19820-115">Метод GetSymbolProviderForImage</span><span class="sxs-lookup"><span data-stu-id="19820-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="19820-116">Возвращает поставщика символов для модуля из базового адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="19820-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19820-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="19820-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19820-118">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="19820-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="19820-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="19820-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19820-120">Требования</span><span class="sxs-lookup"><span data-stu-id="19820-120">Requirements</span></span>  
 <span data-ttu-id="19820-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19820-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19820-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19820-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19820-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19820-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19820-124">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19820-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19820-125">См. также</span><span class="sxs-lookup"><span data-stu-id="19820-125">See Also</span></span>  
 [<span data-ttu-id="19820-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="19820-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="19820-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="19820-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
