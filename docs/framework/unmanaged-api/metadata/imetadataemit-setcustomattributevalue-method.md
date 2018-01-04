---
title: "Метод IMetaDataEmit::SetCustomAttributeValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetCustomAttributeValue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6900fe9edd8c551952691ab02042e5172a39d626
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="7ec8b-102">Метод IMetaDataEmit::SetCustomAttributeValue</span><span class="sxs-lookup"><span data-stu-id="7ec8b-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="7ec8b-103">Задает или обновляет значение настраиваемого атрибута определен во время предыдущего вызова для [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="7ec8b-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec8b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ec8b-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ec8b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ec8b-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="7ec8b-106">[in] Токен настраиваемого атрибута target.</span><span class="sxs-lookup"><span data-stu-id="7ec8b-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="7ec8b-107">[in] Указатель на массив, содержащий пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="7ec8b-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="7ec8b-108">[in] Размер в байтах настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="7ec8b-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec8b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7ec8b-109">Requirements</span></span>  
 <span data-ttu-id="7ec8b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ec8b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ec8b-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ec8b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ec8b-112">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ec8b-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ec8b-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec8b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ec8b-114">See Also</span></span>  
 [<span data-ttu-id="7ec8b-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7ec8b-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7ec8b-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7ec8b-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
