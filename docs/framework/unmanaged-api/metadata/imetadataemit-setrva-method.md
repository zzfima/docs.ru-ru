---
title: Метод IMetaDataEmit::SetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e17a6846ba0276ec7ba423ab25e3f11baf278d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098758"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="27408-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="27408-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="27408-103">Задает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="27408-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27408-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27408-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27408-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27408-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="27408-106">[in] Маркер целевого метода или реализации метода.</span><span class="sxs-lookup"><span data-stu-id="27408-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="27408-107">[in] Адрес области кода или данных.</span><span class="sxs-lookup"><span data-stu-id="27408-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27408-108">Требования</span><span class="sxs-lookup"><span data-stu-id="27408-108">Requirements</span></span>  
 <span data-ttu-id="27408-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27408-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27408-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27408-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27408-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27408-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="27408-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="27408-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27408-113">См. также</span><span class="sxs-lookup"><span data-stu-id="27408-113">See also</span></span>

- [<span data-ttu-id="27408-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="27408-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="27408-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="27408-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
