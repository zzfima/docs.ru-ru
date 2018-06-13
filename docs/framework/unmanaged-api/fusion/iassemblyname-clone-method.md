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
ms.openlocfilehash: ee16193c95c9e754f5bff9aeaf37ff74c456891e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428472"
---
# <a name="iassemblynameclone-method"></a><span data-ttu-id="4479c-102">Метод IAssemblyName::Clone</span><span class="sxs-lookup"><span data-stu-id="4479c-102">IAssemblyName::Clone Method</span></span>
<span data-ttu-id="4479c-103">Создает неполную копию [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="4479c-103">Creates a shallow copy of this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4479c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4479c-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] IAssemblyName **pName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4479c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4479c-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="4479c-106">[out] Возвращаемый копию данного объекта `IAssemblyName` объекта.</span><span class="sxs-lookup"><span data-stu-id="4479c-106">[out] The returned copy of this `IAssemblyName` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4479c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4479c-107">Requirements</span></span>  
 <span data-ttu-id="4479c-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4479c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4479c-109">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4479c-109">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4479c-110">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4479c-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4479c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4479c-111">See Also</span></span>  
 [<span data-ttu-id="4479c-112">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="4479c-112">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
