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
ms.openlocfilehash: c1a9df30ae11b13c052c75b05b0850d9f4754620
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470098"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="bd1df-102">Метод IMetaDataEmit::SetRVA</span><span class="sxs-lookup"><span data-stu-id="bd1df-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="bd1df-103">Задает относительный виртуальный адрес указанного метода.</span><span class="sxs-lookup"><span data-stu-id="bd1df-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd1df-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd1df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd1df-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="bd1df-106">[in] Маркер целевого метода или реализации метода.</span><span class="sxs-lookup"><span data-stu-id="bd1df-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="bd1df-107">[in] Адрес области кода или данных.</span><span class="sxs-lookup"><span data-stu-id="bd1df-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1df-108">Требования</span><span class="sxs-lookup"><span data-stu-id="bd1df-108">Requirements</span></span>  
 <span data-ttu-id="bd1df-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd1df-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1df-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd1df-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd1df-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd1df-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd1df-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1df-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1df-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bd1df-113">See also</span></span>
- [<span data-ttu-id="bd1df-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bd1df-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bd1df-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bd1df-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
