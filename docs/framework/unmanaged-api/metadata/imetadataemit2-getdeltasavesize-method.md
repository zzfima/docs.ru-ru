---
title: "Метод IMetaDataEmit2::GetDeltaSaveSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.GetDeltaSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562b7be418a4a4e335350adf5131178e406b5a07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2getdeltasavesize-method"></a><span data-ttu-id="306db-102">Метод IMetaDataEmit2::GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="306db-102">IMetaDataEmit2::GetDeltaSaveSize Method</span></span>
<span data-ttu-id="306db-103">Возвращает значение, указывающее, любое изменение в размере метаданных, из текущего сеанса edit-and-continue.</span><span class="sxs-lookup"><span data-stu-id="306db-103">Gets a value indicating any change in metadata size that results from the current edit-and-continue session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="306db-104">Syntax</span></span>  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="306db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="306db-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="306db-106">[in] Один из [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) , указывающие уровень точности требуемого значения.</span><span class="sxs-lookup"><span data-stu-id="306db-106">[in] One of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) values, indicating the level of precision desired.</span></span> <span data-ttu-id="306db-107">Этот параметр учитывается для платформы .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="306db-107">For the .NET Framework version 2.0, this parameter is ignored.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="306db-108">[out] Изменение размера метаданных.</span><span class="sxs-lookup"><span data-stu-id="306db-108">[out] The change in the size of the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306db-109">Требования</span><span class="sxs-lookup"><span data-stu-id="306db-109">Requirements</span></span>  
 <span data-ttu-id="306db-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306db-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="306db-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="306db-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="306db-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="306db-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306db-114">См. также</span><span class="sxs-lookup"><span data-stu-id="306db-114">See Also</span></span>  
 [<span data-ttu-id="306db-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="306db-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="306db-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="306db-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
