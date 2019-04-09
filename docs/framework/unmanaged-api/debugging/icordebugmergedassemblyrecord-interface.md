---
title: Интерфейс ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180470"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="d27ce-102">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="d27ce-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="d27ce-103">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="d27ce-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d27ce-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d27ce-104">Methods</span></span>  
  
|<span data-ttu-id="d27ce-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d27ce-105">Method</span></span>|<span data-ttu-id="d27ce-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d27ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d27ce-107">Метод GetCulture</span><span class="sxs-lookup"><span data-stu-id="d27ce-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="d27ce-108">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="d27ce-109">Метод GetIndex</span><span class="sxs-lookup"><span data-stu-id="d27ce-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="d27ce-110">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="d27ce-111">Метод GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="d27ce-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="d27ce-112">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="d27ce-113">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="d27ce-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="d27ce-114">Возвращает токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="d27ce-115">Метод GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="d27ce-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="d27ce-116">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="d27ce-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="d27ce-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="d27ce-118">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="d27ce-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d27ce-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="d27ce-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d27ce-120">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d27ce-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d27ce-121">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d27ce-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27ce-122">Требования</span><span class="sxs-lookup"><span data-stu-id="d27ce-122">Requirements</span></span>  
 <span data-ttu-id="d27ce-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d27ce-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27ce-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d27ce-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d27ce-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27ce-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d27ce-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d27ce-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d27ce-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d27ce-127">See also</span></span>

- [<span data-ttu-id="d27ce-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d27ce-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d27ce-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="d27ce-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
