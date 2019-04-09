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
ms.openlocfilehash: 78f2405bba9172b775b01e5417860c3f3d2dd4a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206932"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="6bbaf-102">Метод IMetaDataEmit::DeleteFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="6bbaf-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="6bbaf-103">Уничтожает PInvoke, маршалинг подпись метаданных для объекта, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="6bbaf-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bbaf-104">Syntax</span></span>  
  
```  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bbaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bbaf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6bbaf-106">[in] `mdFieldDef` Или `mdParamDef` токен, представляющий поля или параметра, для которого необходимо удалить маршалинга подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="6bbaf-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bbaf-107">Требования</span><span class="sxs-lookup"><span data-stu-id="6bbaf-107">Requirements</span></span>  
 <span data-ttu-id="6bbaf-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bbaf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bbaf-109">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6bbaf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6bbaf-110">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bbaf-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6bbaf-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6bbaf-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6bbaf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6bbaf-112">See also</span></span>

- [<span data-ttu-id="6bbaf-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6bbaf-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6bbaf-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6bbaf-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
