---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: ca5bb822be515c936560eb4888c72ea306888ff3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791492"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="8a8a3-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="8a8a3-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="8a8a3-103">Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="8a8a3-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a8a3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8a8a3-104">Methods</span></span>  
  
|<span data-ttu-id="8a8a3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8a8a3-105">Method</span></span>|<span data-ttu-id="8a8a3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8a8a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a8a3-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="8a8a3-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="8a8a3-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="8a8a3-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="8a8a3-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="8a8a3-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="8a8a3-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="8a8a3-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a8a3-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a8a3-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a8a3-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8a8a3-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8a8a3-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8a8a3-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a8a3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8a8a3-114">Requirements</span></span>  
 <span data-ttu-id="8a8a3-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a8a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a8a3-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a8a3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a8a3-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a8a3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a8a3-118">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a8a3-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a8a3-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a8a3-119">See also</span></span>

- [<span data-ttu-id="8a8a3-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8a8a3-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8a8a3-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8a8a3-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a8a3-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="8a8a3-122">Debugging</span></span>](index.md)
