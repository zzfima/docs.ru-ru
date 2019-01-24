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
ms.openlocfilehash: 550dddea9be711d5821dbc86ab3ca54ab0d967ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598481"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="6ff14-102">Метод IAssemblyName::Clone</span><span class="sxs-lookup"><span data-stu-id="6ff14-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="6ff14-103">Создает неполную копию этого [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="6ff14-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ff14-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ff14-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ff14-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="6ff14-106">[out] Возвращаемый копию данного объекта `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="6ff14-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ff14-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6ff14-107">Requirements</span></span>  
 <span data-ttu-id="6ff14-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ff14-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ff14-109">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6ff14-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6ff14-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ff14-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff14-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6ff14-111">See also</span></span>
- [<span data-ttu-id="6ff14-112">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6ff14-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
