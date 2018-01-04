---
title: "Метод IMetaDataEmit::DeleteToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeleteToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeleteToken
helpviewer_keywords:
- DeleteToken method [.NET Framework metadata]
- IMetaDataEmit::DeleteToken method [.NET Framework metadata]
ms.assetid: a4926d0a-261b-46b1-9994-82633661a64b
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5fe79e13a44ef9d916a0009c46200605950e8895
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletetoken-method"></a><span data-ttu-id="b67db-102">Метод IMetaDataEmit::DeleteToken</span><span class="sxs-lookup"><span data-stu-id="b67db-102">IMetaDataEmit::DeleteToken Method</span></span>
<span data-ttu-id="b67db-103">Удаляет указанный маркер из текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="b67db-103">Deletes the specified token from the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b67db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b67db-104">Syntax</span></span>  
  
```  
HRESULT DeleteToken (   
    [in]  mdToken     tkObj   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b67db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b67db-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="b67db-106">[in] Токен для удаления.</span><span class="sxs-lookup"><span data-stu-id="b67db-106">[in] The token to be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b67db-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b67db-107">Requirements</span></span>  
 <span data-ttu-id="b67db-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b67db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b67db-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b67db-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b67db-110">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b67db-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b67db-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b67db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67db-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b67db-112">See Also</span></span>  
 [<span data-ttu-id="b67db-113">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b67db-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b67db-114">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b67db-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
