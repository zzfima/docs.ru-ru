---
title: Метод IAssemblyName::Clone
ms.date: 03/30/2017
api_name:
- IAssemblyName.Clone
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Clone
helpviewer_keywords:
- Clone method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::Clone method [.NET Framework fusion]
ms.assetid: 7b345e08-5e16-4e3d-a044-4e19d0892943
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bf67506fca161a64dd5d4ee915031c155c49241
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754027"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="d7f6d-102">Метод IAssemblyName::Clone</span><span class="sxs-lookup"><span data-stu-id="d7f6d-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="d7f6d-103">Создает неполную копию этого [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="d7f6d-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7f6d-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7f6d-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d7f6d-106">[out] Возвращаемый копию данного объекта `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="d7f6d-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f6d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d7f6d-107">Requirements</span></span>  
 <span data-ttu-id="d7f6d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f6d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f6d-109">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d7f6d-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d7f6d-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f6d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f6d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d7f6d-111">See also</span></span>

- [<span data-ttu-id="d7f6d-112">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="d7f6d-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
