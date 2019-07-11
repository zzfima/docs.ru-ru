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
ms.openlocfilehash: c6006c8892f650eec9528074d54f030d84ee8f88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750885"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="35a96-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="35a96-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="35a96-103">Определяет, что указанный член, в соответствии с предыдущего вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является членом указанного типа, в соответствии с определением предыдущего вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="35a96-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35a96-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35a96-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35a96-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="35a96-106">[in] `mdMemberRef` Маркер, чтобы получить новый родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="35a96-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="35a96-107">[in] `mdToken` Нового родителя.</span><span class="sxs-lookup"><span data-stu-id="35a96-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a96-108">Требования</span><span class="sxs-lookup"><span data-stu-id="35a96-108">Requirements</span></span>  
 <span data-ttu-id="35a96-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a96-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a96-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35a96-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35a96-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35a96-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35a96-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a96-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a96-113">См. также</span><span class="sxs-lookup"><span data-stu-id="35a96-113">See also</span></span>

- [<span data-ttu-id="35a96-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="35a96-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="35a96-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="35a96-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
