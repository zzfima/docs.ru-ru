---
title: "Интерфейс ICorDebugSymbolProvider2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff0446ba8646620cb7322f74a81769e41f35b0d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="ceef3-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="ceef3-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="ceef3-103">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для получения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="ceef3-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ceef3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ceef3-104">Methods</span></span>  
  
|<span data-ttu-id="ceef3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ceef3-105">Method</span></span>|<span data-ttu-id="ceef3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ceef3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ceef3-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="ceef3-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="ceef3-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="ceef3-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="ceef3-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="ceef3-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="ceef3-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="ceef3-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceef3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ceef3-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceef3-112">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ceef3-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ceef3-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ceef3-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceef3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ceef3-114">Requirements</span></span>  
 <span data-ttu-id="ceef3-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceef3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceef3-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ceef3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ceef3-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceef3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceef3-118">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceef3-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceef3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ceef3-119">See Also</span></span>  
 [<span data-ttu-id="ceef3-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="ceef3-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="ceef3-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ceef3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ceef3-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="ceef3-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
