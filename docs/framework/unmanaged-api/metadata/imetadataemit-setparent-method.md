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
ms.openlocfilehash: fe27d8a0508a13c1f54eef00d5119bec4daec4a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043008"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="33e87-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="33e87-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="33e87-103">Определяет, что указанный член, в соответствии с предыдущего вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является членом указанного типа, в соответствии с определением предыдущего вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="33e87-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33e87-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33e87-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33e87-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="33e87-106">[in] `mdMemberRef` Маркер, чтобы получить новый родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="33e87-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="33e87-107">[in] `mdToken` Нового родителя.</span><span class="sxs-lookup"><span data-stu-id="33e87-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e87-108">Требования</span><span class="sxs-lookup"><span data-stu-id="33e87-108">Requirements</span></span>  
 <span data-ttu-id="33e87-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33e87-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e87-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33e87-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33e87-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33e87-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33e87-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e87-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e87-113">См. также</span><span class="sxs-lookup"><span data-stu-id="33e87-113">See also</span></span>

- [<span data-ttu-id="33e87-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="33e87-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="33e87-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="33e87-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
