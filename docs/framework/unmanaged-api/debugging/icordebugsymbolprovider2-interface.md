---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b787302902779695c48df6e02e2ee00b28f44cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142471"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="20746-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="20746-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="20746-103">Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки.</span><span class="sxs-lookup"><span data-stu-id="20746-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20746-104">Методы</span><span class="sxs-lookup"><span data-stu-id="20746-104">Methods</span></span>  
  
|<span data-ttu-id="20746-105">Метод</span><span class="sxs-lookup"><span data-stu-id="20746-105">Method</span></span>|<span data-ttu-id="20746-106">Описание</span><span class="sxs-lookup"><span data-stu-id="20746-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20746-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="20746-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="20746-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="20746-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="20746-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="20746-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="20746-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="20746-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20746-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="20746-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20746-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="20746-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="20746-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="20746-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20746-114">Требования</span><span class="sxs-lookup"><span data-stu-id="20746-114">Requirements</span></span>  
 <span data-ttu-id="20746-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20746-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20746-116">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20746-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20746-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20746-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="20746-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="20746-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20746-119">См. также</span><span class="sxs-lookup"><span data-stu-id="20746-119">See also</span></span>

- [<span data-ttu-id="20746-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="20746-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="20746-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="20746-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="20746-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="20746-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
