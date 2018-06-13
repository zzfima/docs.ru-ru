---
title: Метод IMetaDataEmit::SetParent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdaa6aab28eb82450db7b9f946e033bfad55faf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446073"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="0d6a1-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="0d6a1-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="0d6a1-103">Определяет, указанный член, в соответствии с определением в предыдущем вызове [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является членом указанного типа, в соответствии с определением предыдущего вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d6a1-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d6a1-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d6a1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d6a1-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="0d6a1-106">[in] `mdMemberRef` Токен для получения нового родителя.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="0d6a1-107">[in] `mdToken` Нового родителя.</span><span class="sxs-lookup"><span data-stu-id="0d6a1-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d6a1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0d6a1-108">Requirements</span></span>  
 <span data-ttu-id="0d6a1-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d6a1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6a1-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d6a1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d6a1-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d6a1-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d6a1-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d6a1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6a1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0d6a1-113">See Also</span></span>  
 [<span data-ttu-id="0d6a1-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0d6a1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0d6a1-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0d6a1-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
