---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea60ecd542300bf3833c4977b7f0910399a2e409
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504032"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="6d828-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="6d828-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="6d828-103">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="6d828-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6d828-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6d828-104">Methods</span></span>  
  
|<span data-ttu-id="6d828-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6d828-105">Method</span></span>|<span data-ttu-id="6d828-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="6d828-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6d828-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="6d828-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="6d828-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="6d828-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="6d828-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="6d828-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="6d828-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="6d828-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d828-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d828-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d828-112">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6d828-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6d828-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="6d828-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d828-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6d828-114">Requirements</span></span>  
 <span data-ttu-id="6d828-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d828-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d828-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d828-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d828-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d828-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d828-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d828-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d828-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6d828-119">See also</span></span>
- [<span data-ttu-id="6d828-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6d828-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6d828-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6d828-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6d828-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="6d828-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
