---
title: Метод IMetaDataEmit::DeleteFieldMarshal
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc88baea130adbec3dd8e4065ac0eb14ece7b8ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444855"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="55c3b-102">Метод IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="55c3b-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="55c3b-103">Удаляет подпись метаданных для объекта, который ссылается указанный токен маршалинга PInvoke.</span><span class="sxs-lookup"><span data-stu-id="55c3b-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c3b-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55c3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55c3b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="55c3b-106">[in] `mdFieldDef` Или `mdParamDef` токен, представляющий поля или параметра, для которого требуется удалить подпись метаданных маршалинга.</span><span class="sxs-lookup"><span data-stu-id="55c3b-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c3b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="55c3b-107">Requirements</span></span>  
 <span data-ttu-id="55c3b-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c3b-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="55c3b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55c3b-110">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55c3b-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55c3b-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c3b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c3b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="55c3b-112">See Also</span></span>  
 [<span data-ttu-id="55c3b-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="55c3b-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="55c3b-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="55c3b-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
