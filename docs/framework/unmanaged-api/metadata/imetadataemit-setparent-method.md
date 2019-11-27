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
ms.openlocfilehash: a73afaebc2943190eeeee50367ecd31f1fb59df1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432450"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="9c270-102">Метод IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="9c270-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="9c270-103">Устанавливает, что указанный элемент, как определено в предыдущем вызове [IMetaDataEmit::D ефинемемберреф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), является членом указанного типа, как определено в предыдущем вызове [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="9c270-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c270-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c270-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c270-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c270-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="9c270-106">окне Токен `mdMemberRef` для получения нового родителя.</span><span class="sxs-lookup"><span data-stu-id="9c270-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="9c270-107">окне `mdToken` для нового родителя.</span><span class="sxs-lookup"><span data-stu-id="9c270-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c270-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9c270-108">Requirements</span></span>  
 <span data-ttu-id="9c270-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c270-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c270-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9c270-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c270-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c270-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c270-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c270-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c270-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9c270-113">See also</span></span>

- [<span data-ttu-id="9c270-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9c270-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9c270-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9c270-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
