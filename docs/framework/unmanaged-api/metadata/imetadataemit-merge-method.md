---
title: Метод IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175711"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="e61d0-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="e61d0-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="e61d0-103">Добавляет указанную импортируемую область в список областей, которые должны быть объединены.</span><span class="sxs-lookup"><span data-stu-id="e61d0-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e61d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e61d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e61d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e61d0-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="e61d0-106">(в) Указатель на объект [IMetaDataImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) который определяет импортируемую область, подкоторую поднимую.</span><span class="sxs-lookup"><span data-stu-id="e61d0-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="e61d0-107">(в) Указатель на объект [IMapToken,](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) который определяет повторную карту токена.</span><span class="sxs-lookup"><span data-stu-id="e61d0-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="e61d0-108">(в) Указатель на объект [IUnknown,](/cpp/atl/iunknown) который определяет ошибки.</span><span class="sxs-lookup"><span data-stu-id="e61d0-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e61d0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e61d0-109">Remarks</span></span>  
 <span data-ttu-id="e61d0-110">Позвоните [IMetaDataEmit::MergeEnd,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) чтобы запустить слияние метаданных в единую область.</span><span class="sxs-lookup"><span data-stu-id="e61d0-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e61d0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e61d0-111">Requirements</span></span>  
 <span data-ttu-id="e61d0-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e61d0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e61d0-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e61d0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e61d0-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e61d0-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e61d0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e61d0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61d0-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e61d0-116">See also</span></span>

- [<span data-ttu-id="e61d0-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e61d0-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e61d0-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e61d0-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
