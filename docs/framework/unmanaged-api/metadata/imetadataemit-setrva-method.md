---
title: "Метод IMetaDataEmit::SetRVA"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25f0e20e1249067dfd9162b84c07b38e9b97de15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="e2e2b-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="e2e2b-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="e2e2b-103">Задает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="e2e2b-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2e2b-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2e2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2e2b-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="e2e2b-106">[in] Токен для целевого метода или реализации метода.</span><span class="sxs-lookup"><span data-stu-id="e2e2b-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="e2e2b-107">[in] Адрес области кода или данных.</span><span class="sxs-lookup"><span data-stu-id="e2e2b-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e2b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="e2e2b-108">Requirements</span></span>  
 <span data-ttu-id="e2e2b-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e2b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e2b-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2e2b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2e2b-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2e2b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2e2b-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e2b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e2b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e2e2b-113">See Also</span></span>  
 [<span data-ttu-id="e2e2b-114">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="e2e2b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e2e2b-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e2e2b-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
