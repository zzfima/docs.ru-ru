---
title: Интерфейс ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793058"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="a9d62-102">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="a9d62-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="a9d62-103">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="a9d62-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9d62-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a9d62-104">Methods</span></span>  
  
|<span data-ttu-id="a9d62-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a9d62-105">Method</span></span>|<span data-ttu-id="a9d62-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a9d62-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9d62-107">Метод GetCulture</span><span class="sxs-lookup"><span data-stu-id="a9d62-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="a9d62-108">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="a9d62-109">Метод GetIndex</span><span class="sxs-lookup"><span data-stu-id="a9d62-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="a9d62-110">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="a9d62-111">Метод GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a9d62-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="a9d62-112">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="a9d62-113">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="a9d62-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="a9d62-114">Возвращает токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="a9d62-115">Метод GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="a9d62-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="a9d62-116">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="a9d62-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="a9d62-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="a9d62-118">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="a9d62-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9d62-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="a9d62-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9d62-120">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a9d62-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a9d62-121">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a9d62-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d62-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a9d62-122">Requirements</span></span>  
 <span data-ttu-id="a9d62-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9d62-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d62-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9d62-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9d62-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9d62-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9d62-126">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9d62-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d62-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="a9d62-127">See also</span></span>

- [<span data-ttu-id="a9d62-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a9d62-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a9d62-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="a9d62-129">Debugging</span></span>](index.md)
