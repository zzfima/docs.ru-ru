---
title: "Метод IMetaDataEmit::DeleteFieldMarshal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ce60aace95f4da8c021026cf9bfc6c195de5b05f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="67e55-102">Метод IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="67e55-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="67e55-103">Удаляет подпись метаданных для объекта, который ссылается указанный токен маршалинга PInvoke.</span><span class="sxs-lookup"><span data-stu-id="67e55-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e55-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67e55-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67e55-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67e55-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="67e55-106">[in] `mdFieldDef` Или `mdParamDef` токен, представляющий поля или параметра, для которого требуется удалить подпись метаданных маршалинга.</span><span class="sxs-lookup"><span data-stu-id="67e55-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e55-107">Требования</span><span class="sxs-lookup"><span data-stu-id="67e55-107">Requirements</span></span>  
 <span data-ttu-id="67e55-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e55-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e55-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67e55-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67e55-110">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67e55-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67e55-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e55-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e55-112">См. также</span><span class="sxs-lookup"><span data-stu-id="67e55-112">See Also</span></span>  
 [<span data-ttu-id="67e55-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="67e55-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="67e55-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="67e55-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
