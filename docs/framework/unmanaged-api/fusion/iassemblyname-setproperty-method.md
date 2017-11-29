---
title: "Метод IAssemblyName::SetProperty"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.SetProperty
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b99b9c01d014f7b6c02eedde157fa6fdd4e142a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="37b2b-102">Метод IAssemblyName::SetProperty</span><span class="sxs-lookup"><span data-stu-id="37b2b-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="37b2b-103">Задает значение свойства, который ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="37b2b-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37b2b-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37b2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37b2b-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="37b2b-106">[in] Уникальный идентификатор свойства, значение которого будет установлено.</span><span class="sxs-lookup"><span data-stu-id="37b2b-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="37b2b-107">[in] Значение, которое необходимо задать свойство ссылается `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="37b2b-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="37b2b-108">[in] Размер в байтах для `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="37b2b-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b2b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="37b2b-109">Requirements</span></span>  
 <span data-ttu-id="37b2b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37b2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b2b-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="37b2b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="37b2b-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b2b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b2b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="37b2b-113">See Also</span></span>  
 [<span data-ttu-id="37b2b-114">IAssemblyName-интерфейс</span><span class="sxs-lookup"><span data-stu-id="37b2b-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
