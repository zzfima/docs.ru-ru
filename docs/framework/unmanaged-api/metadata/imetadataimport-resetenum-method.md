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
ms.openlocfilehash: 56fc0273fb2c1b77c74d7a1d853886f47170497e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="b2e27-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="b2e27-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="b2e27-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="b2e27-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2e27-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2e27-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2e27-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b2e27-106">[in] Чтобы сбросить перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b2e27-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="b2e27-107">[in] Новая позиция, в который требуется поместить перечислитель.</span><span class="sxs-lookup"><span data-stu-id="b2e27-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2e27-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b2e27-108">Requirements</span></span>  
 <span data-ttu-id="b2e27-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2e27-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2e27-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2e27-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2e27-111">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2e27-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2e27-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2e27-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e27-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b2e27-113">See Also</span></span>  
 [<span data-ttu-id="b2e27-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b2e27-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b2e27-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b2e27-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
