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
ms.openlocfilehash: b680e807554a60711e61729680e9c9fcf1c8fdaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="69054-102">Метод IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="69054-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="69054-103">Сохраняет все метаданные в текущей области в указанной области памяти.</span><span class="sxs-lookup"><span data-stu-id="69054-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69054-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69054-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69054-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69054-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="69054-106">[out] Адрес, с которого начинается запись метаданных.</span><span class="sxs-lookup"><span data-stu-id="69054-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="69054-107">[in] Размер в байтах, выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="69054-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69054-108">Требования</span><span class="sxs-lookup"><span data-stu-id="69054-108">Requirements</span></span>  
 <span data-ttu-id="69054-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69054-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69054-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69054-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69054-111">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69054-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69054-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69054-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69054-113">См. также</span><span class="sxs-lookup"><span data-stu-id="69054-113">See Also</span></span>  
 [<span data-ttu-id="69054-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="69054-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="69054-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="69054-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
