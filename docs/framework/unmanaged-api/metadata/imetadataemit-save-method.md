---
title: Метод IMetaDataEmit::Save
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435948"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="1d368-102">Метод IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="1d368-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="1d368-103">Saves all metadata in the current scope to the file at the specified address.</span><span class="sxs-lookup"><span data-stu-id="1d368-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d368-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d368-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d368-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d368-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="1d368-106">[in] The name of the file to save to.</span><span class="sxs-lookup"><span data-stu-id="1d368-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="1d368-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span><span class="sxs-lookup"><span data-stu-id="1d368-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="1d368-108">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="1d368-108">[in] Reserved.</span></span> <span data-ttu-id="1d368-109">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="1d368-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d368-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1d368-110">Requirements</span></span>  
 <span data-ttu-id="1d368-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d368-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d368-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d368-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d368-113">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d368-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d368-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d368-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d368-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1d368-115">See also</span></span>

- [<span data-ttu-id="1d368-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1d368-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1d368-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1d368-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
