---
title: Метод IAssemblyName::SetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcfb584fc2380a7ae1567d3d4d6203b537676220
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429703"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="36bff-102">Метод IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="36bff-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="36bff-103">Задает значение свойства, который ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="36bff-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36bff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="36bff-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36bff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="36bff-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="36bff-106">[in] Уникальный идентификатор свойства, значение которого будет установлено.</span><span class="sxs-lookup"><span data-stu-id="36bff-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="36bff-107">[in] Значение, которое необходимо задать свойство ссылается `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="36bff-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="36bff-108">[in] Размер в байтах для `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="36bff-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36bff-109">Требования</span><span class="sxs-lookup"><span data-stu-id="36bff-109">Requirements</span></span>  
 <span data-ttu-id="36bff-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36bff-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36bff-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="36bff-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="36bff-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36bff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36bff-113">См. также</span><span class="sxs-lookup"><span data-stu-id="36bff-113">See Also</span></span>  
 [<span data-ttu-id="36bff-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="36bff-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
