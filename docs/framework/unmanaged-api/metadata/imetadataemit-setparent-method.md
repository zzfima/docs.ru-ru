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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175607"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="771d0-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="771d0-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="771d0-103">Устанавливает, что указанный участник, как это определено предварительным вызовом [в IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является участником указанного типа, как это определено предварительным вызовом [на IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="771d0-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="771d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="771d0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="771d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="771d0-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="771d0-106">(в) Токен `mdMemberRef` для получения нового родительского.</span><span class="sxs-lookup"><span data-stu-id="771d0-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="771d0-107">(в) Для `mdToken` нового родителя.</span><span class="sxs-lookup"><span data-stu-id="771d0-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="771d0-108">Требования</span><span class="sxs-lookup"><span data-stu-id="771d0-108">Requirements</span></span>  
 <span data-ttu-id="771d0-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="771d0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="771d0-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="771d0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="771d0-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="771d0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="771d0-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="771d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771d0-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="771d0-113">See also</span></span>

- [<span data-ttu-id="771d0-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="771d0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="771d0-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="771d0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
