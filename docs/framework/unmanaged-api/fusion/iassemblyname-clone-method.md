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
ms.openlocfilehash: 2c824874d340aa3d381b3340408021ef1ed7eec6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166703"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="46b1a-102">Метод IAssemblyName::Clone</span><span class="sxs-lookup"><span data-stu-id="46b1a-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="46b1a-103">Создает неполную копию этого [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="46b1a-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b1a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46b1a-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b1a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46b1a-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="46b1a-106">[out] Возвращаемый копию данного объекта `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="46b1a-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b1a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="46b1a-107">Requirements</span></span>  
 <span data-ttu-id="46b1a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46b1a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b1a-109">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="46b1a-109">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="46b1a-110">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="46b1a-110">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46b1a-111">См. также</span><span class="sxs-lookup"><span data-stu-id="46b1a-111">See also</span></span>

- [<span data-ttu-id="46b1a-112">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="46b1a-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
