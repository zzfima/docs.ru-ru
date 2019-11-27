---
title: Метод IMetaDataEmit::DeleteClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: 00f2aa3364b8b707d4100f8d2574ff3765d106da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450165"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="aa984-102">Метод IMetaDataEmit::DeleteClassLayout</span><span class="sxs-lookup"><span data-stu-id="aa984-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="aa984-103">Уничтожает сигнатуру метаданных макета класса для типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="aa984-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa984-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa984-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa984-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa984-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="aa984-106">окне `mdTypeDef`ный маркер метаданных, представляющий тип, для которого будет удален макет класса.</span><span class="sxs-lookup"><span data-stu-id="aa984-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa984-107">Требования</span><span class="sxs-lookup"><span data-stu-id="aa984-107">Requirements</span></span>  
 <span data-ttu-id="aa984-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa984-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa984-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="aa984-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa984-110">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa984-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa984-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa984-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa984-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa984-112">See also</span></span>

- [<span data-ttu-id="aa984-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="aa984-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa984-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="aa984-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
