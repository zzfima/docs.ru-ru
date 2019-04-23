---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b787302902779695c48df6e02e2ee00b28f44cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142471"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="bc216-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="bc216-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="bc216-103">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="bc216-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bc216-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bc216-104">Methods</span></span>  
  
|<span data-ttu-id="bc216-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bc216-105">Method</span></span>|<span data-ttu-id="bc216-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bc216-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc216-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="bc216-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="bc216-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="bc216-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="bc216-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="bc216-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="bc216-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="bc216-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc216-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc216-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc216-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bc216-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="bc216-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc216-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc216-114">Требования</span><span class="sxs-lookup"><span data-stu-id="bc216-114">Requirements</span></span>  
 <span data-ttu-id="bc216-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc216-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc216-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc216-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc216-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc216-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc216-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc216-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc216-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bc216-119">See also</span></span>

- [<span data-ttu-id="bc216-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="bc216-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="bc216-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bc216-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bc216-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="bc216-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
