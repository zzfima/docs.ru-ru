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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fee3c0b82bec102d8e292a76d3df5a14d40ace8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757669"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="00389-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="00389-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="00389-103">Добавляет указанный импортируемой области в список объединяемых областей.</span><span class="sxs-lookup"><span data-stu-id="00389-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00389-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00389-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00389-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00389-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="00389-106">[in] Указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , идентифицирующий импортируемой области для слияния.</span><span class="sxs-lookup"><span data-stu-id="00389-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="00389-107">[in] Указатель на [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) , указывающий маркера повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="00389-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="00389-108">[in] Указатель на [IUnknown](/cpp/atl/iunknown) , указывающий ошибки.</span><span class="sxs-lookup"><span data-stu-id="00389-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00389-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="00389-109">Remarks</span></span>  
 <span data-ttu-id="00389-110">Вызовите [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) для запуска средства слияния метаданных в одной области.</span><span class="sxs-lookup"><span data-stu-id="00389-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00389-111">Требования</span><span class="sxs-lookup"><span data-stu-id="00389-111">Requirements</span></span>  
 <span data-ttu-id="00389-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00389-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00389-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00389-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00389-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00389-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00389-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00389-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00389-116">См. также</span><span class="sxs-lookup"><span data-stu-id="00389-116">See also</span></span>

- [<span data-ttu-id="00389-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="00389-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="00389-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="00389-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
