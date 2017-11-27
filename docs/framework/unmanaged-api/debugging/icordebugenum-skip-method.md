---
title: "Метод ICorDebugEnum::Skip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.Skip
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d109d8e28f94edc3eeceeb22d2d0639d010b532e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="a3f09-102">Метод ICorDebugEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="a3f09-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="a3f09-103">Перемещение курсора вперед в перечислении указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="a3f09-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a3f09-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3f09-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a3f09-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a3f09-106">[in] Количество элементов, с помощью которого для перемещения курсора вперед.</span><span class="sxs-lookup"><span data-stu-id="a3f09-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f09-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a3f09-107">Requirements</span></span>  
 <span data-ttu-id="a3f09-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f09-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f09-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3f09-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3f09-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3f09-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3f09-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f09-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f09-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a3f09-112">See Also</span></span>  
 [<span data-ttu-id="a3f09-113">ICorDebugEnum интерфейс1</span><span class="sxs-lookup"><span data-stu-id="a3f09-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
