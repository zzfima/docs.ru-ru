---
title: "Метод IMetaDataEmit::Merge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Merge
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f05f2e39365b021e902b2bdaa41cda481b5af8b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="039d5-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="039d5-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="039d5-103">Добавляет заданную импортируемую область в список объединяемых областей.</span><span class="sxs-lookup"><span data-stu-id="039d5-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="039d5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="039d5-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="039d5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="039d5-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="039d5-106">[in] Указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) объект, определяющий область, импортированных для слияния.</span><span class="sxs-lookup"><span data-stu-id="039d5-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="039d5-107">[in] Указатель на [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) , указывающий повторного сопоставления маркеров.</span><span class="sxs-lookup"><span data-stu-id="039d5-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="039d5-108">[in] Указатель на <!--<<!--zzxref:IUnknown --> `IUnknown` >-->  `IUnknown` , указывающий ошибки.</span><span class="sxs-lookup"><span data-stu-id="039d5-108">[in] A pointer to an <!--<<!--zzxref:IUnknown --> `IUnknown`>--> `IUnknown` object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="039d5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="039d5-109">Remarks</span></span>  
 <span data-ttu-id="039d5-110">Вызовите [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) для запуска средства слияния метаданных в одной области.</span><span class="sxs-lookup"><span data-stu-id="039d5-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="039d5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="039d5-111">Requirements</span></span>  
 <span data-ttu-id="039d5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="039d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="039d5-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="039d5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="039d5-114">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="039d5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="039d5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="039d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039d5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="039d5-116">See Also</span></span>  
 [<span data-ttu-id="039d5-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="039d5-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="039d5-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="039d5-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
