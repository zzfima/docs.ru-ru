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
ms.openlocfilehash: 179cfc5c0725934e21d7b89a2f8d4c934b049f78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106059"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="a7b01-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="a7b01-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="a7b01-103">Добавляет указанный импортируемой области в список объединяемых областей.</span><span class="sxs-lookup"><span data-stu-id="a7b01-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7b01-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7b01-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="a7b01-106">[in] Указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) , идентифицирующий импортируемой области для слияния.</span><span class="sxs-lookup"><span data-stu-id="a7b01-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="a7b01-107">[in] Указатель на [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) , указывающий маркера повторного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="a7b01-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="a7b01-108">[in] Указатель на [IUnknown](/cpp/atl/iunknown) , указывающий ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7b01-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7b01-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7b01-109">Remarks</span></span>  
 <span data-ttu-id="a7b01-110">Вызовите [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) для запуска средства слияния метаданных в одной области.</span><span class="sxs-lookup"><span data-stu-id="a7b01-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7b01-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a7b01-111">Requirements</span></span>  
 <span data-ttu-id="a7b01-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b01-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b01-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a7b01-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a7b01-114">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7b01-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7b01-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a7b01-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7b01-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a7b01-116">See also</span></span>

- [<span data-ttu-id="a7b01-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a7b01-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a7b01-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a7b01-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
