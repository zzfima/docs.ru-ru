---
title: Метод IMetaDataImport::ResetEnum
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bdd41e884caa5ed39dff4f4f1e027cde1fec53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568014"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="c5177-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="c5177-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="c5177-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="c5177-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5177-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5177-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5177-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5177-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c5177-106">[in] Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="c5177-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="c5177-107">[in] Новое положение, по которому следует вставить перечислитель.</span><span class="sxs-lookup"><span data-stu-id="c5177-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5177-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c5177-108">Requirements</span></span>  
 <span data-ttu-id="c5177-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5177-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5177-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5177-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5177-111">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5177-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5177-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5177-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5177-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c5177-113">See also</span></span>
- [<span data-ttu-id="c5177-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c5177-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c5177-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c5177-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
