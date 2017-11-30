---
title: "Интерфейс ICorDebugMergedAssemblyRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 301d7d3d20b78e833101de1df8fd5c271a757144
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="631d2-102">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="631d2-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="631d2-103">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="631d2-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="631d2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="631d2-104">Methods</span></span>  
  
|<span data-ttu-id="631d2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="631d2-105">Method</span></span>|<span data-ttu-id="631d2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="631d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="631d2-107">Метод GetCulture</span><span class="sxs-lookup"><span data-stu-id="631d2-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="631d2-108">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="631d2-109">GetIndex-метод</span><span class="sxs-lookup"><span data-stu-id="631d2-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="631d2-110">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="631d2-111">Метод GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="631d2-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="631d2-112">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="631d2-113">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="631d2-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="631d2-114">Возвращает токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="631d2-115">Метод GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="631d2-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="631d2-116">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="631d2-117">GetVersion-метод</span><span class="sxs-lookup"><span data-stu-id="631d2-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="631d2-118">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="631d2-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="631d2-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="631d2-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="631d2-120">Этот интерфейс доступен только в  .NET Native.</span><span class="sxs-lookup"><span data-stu-id="631d2-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="631d2-121">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="631d2-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="631d2-122">Требования</span><span class="sxs-lookup"><span data-stu-id="631d2-122">Requirements</span></span>  
 <span data-ttu-id="631d2-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="631d2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631d2-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="631d2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="631d2-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="631d2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="631d2-126">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="631d2-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631d2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="631d2-127">See Also</span></span>  
 [<span data-ttu-id="631d2-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="631d2-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="631d2-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="631d2-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
