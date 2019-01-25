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
ms.openlocfilehash: c3b7c116410ce3309d970929580f4ec7f65bd657
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558288"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="c0d4b-102">Метод IMetaDataEmit::DeletePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="c0d4b-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="c0d4b-103">Удаляет метаданные сопоставления PInvoke для объекта, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="c0d4b-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0d4b-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0d4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0d4b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c0d4b-106">[in] `mdFieldDef` Или `mdMethodDef` токен, представляющий объект, для которого требуется удалить метаданные сопоставления PInvoke.</span><span class="sxs-lookup"><span data-stu-id="c0d4b-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d4b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c0d4b-107">Requirements</span></span>  
 <span data-ttu-id="c0d4b-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d4b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d4b-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0d4b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0d4b-110">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0d4b-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0d4b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d4b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d4b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c0d4b-112">See also</span></span>
- [<span data-ttu-id="c0d4b-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c0d4b-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c0d4b-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c0d4b-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
