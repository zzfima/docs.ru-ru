---
title: Метод IMetaDataEmit::SaveToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6e9bb51965b258093321a5dbb19447ec6d6474d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471831"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="c0465-102">Метод IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="c0465-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="c0465-103">Сохраняет все метаданные в текущей области к указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="c0465-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0465-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0465-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0465-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0465-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="c0465-106">[out] Адрес, с которого начинается запись метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0465-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="c0465-107">[in] Размер в байтах, выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="c0465-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0465-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c0465-108">Requirements</span></span>  
 <span data-ttu-id="c0465-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0465-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0465-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0465-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0465-111">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0465-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0465-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0465-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0465-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c0465-113">See also</span></span>
- [<span data-ttu-id="c0465-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c0465-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c0465-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c0465-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
