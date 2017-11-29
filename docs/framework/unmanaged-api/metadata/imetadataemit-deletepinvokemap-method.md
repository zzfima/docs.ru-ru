---
title: "Метод IMetaDataEmit::DeletePinvokeMap"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeletePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef79c7696f9d697d3306634635c5c00bfd1f00c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="e48c7-102">Метод IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="e48c7-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="e48c7-103">Удаляет метаданные сопоставления PInvoke для объекта, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="e48c7-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e48c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e48c7-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e48c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e48c7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e48c7-106">[in] `mdFieldDef` Или `mdMethodDef` токен, представляющий объект, для которого требуется удалить метаданные сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="e48c7-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e48c7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e48c7-107">Requirements</span></span>  
 <span data-ttu-id="e48c7-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e48c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e48c7-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e48c7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e48c7-110">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e48c7-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e48c7-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e48c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48c7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e48c7-112">See Also</span></span>  
 [<span data-ttu-id="e48c7-113">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e48c7-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e48c7-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e48c7-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
