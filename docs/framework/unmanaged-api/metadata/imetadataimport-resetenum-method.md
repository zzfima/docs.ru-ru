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
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163882"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="673ea-102">Метод IMetaDataImport::ResetEnum</span><span class="sxs-lookup"><span data-stu-id="673ea-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="673ea-103">Возвращает заданный перечислитель в указанную позицию.</span><span class="sxs-lookup"><span data-stu-id="673ea-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="673ea-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="673ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="673ea-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="673ea-106">[in] Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="673ea-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="673ea-107">[in] Новое положение, по которому следует вставить перечислитель.</span><span class="sxs-lookup"><span data-stu-id="673ea-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673ea-108">Требования</span><span class="sxs-lookup"><span data-stu-id="673ea-108">Requirements</span></span>  
 <span data-ttu-id="673ea-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="673ea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673ea-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="673ea-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="673ea-111">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="673ea-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="673ea-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="673ea-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="673ea-113">См. также</span><span class="sxs-lookup"><span data-stu-id="673ea-113">See also</span></span>

- [<span data-ttu-id="673ea-114">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="673ea-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="673ea-115">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="673ea-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
