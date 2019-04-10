---
title: Метод IMetaDataEmit::DeletePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea100ff86286cb98db5aa9fa6f3c12f5d318a90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217748"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="98dc9-102">Метод IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="98dc9-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="98dc9-103">Удаляет метаданные сопоставления PInvoke для объекта, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="98dc9-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98dc9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98dc9-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98dc9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98dc9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="98dc9-106">[in] `mdFieldDef` Или `mdMethodDef` токен, представляющий объект, для которого требуется удалить метаданные сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="98dc9-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98dc9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="98dc9-107">Requirements</span></span>  
 <span data-ttu-id="98dc9-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98dc9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98dc9-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98dc9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98dc9-110">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98dc9-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="98dc9-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="98dc9-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="98dc9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="98dc9-112">See also</span></span>

- [<span data-ttu-id="98dc9-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="98dc9-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="98dc9-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="98dc9-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
