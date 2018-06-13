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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 663f2de5acb3aac92c29a19f5f5db16b5355fe89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444787"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="8b2f7-102">Метод IMetaDataEmit::DeleteClassLayout</span><span class="sxs-lookup"><span data-stu-id="8b2f7-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="8b2f7-103">Удаляет подпись метаданных структуры класса для типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="8b2f7-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b2f7-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b2f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b2f7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8b2f7-106">[in] `mdTypeDef` Токен метаданных, представляющий тип, для которого будут удалены макет класса.</span><span class="sxs-lookup"><span data-stu-id="8b2f7-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2f7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8b2f7-107">Requirements</span></span>  
 <span data-ttu-id="8b2f7-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b2f7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2f7-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b2f7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b2f7-110">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b2f7-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b2f7-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2f7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8b2f7-112">See Also</span></span>  
 [<span data-ttu-id="8b2f7-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8b2f7-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8b2f7-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8b2f7-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
