---
title: "Метод IMetaDataFilter::IsTokenMarked"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter.IsTokenMarked
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 832f1e57e55245a84d093a41c627613d5fbe6902
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="9bf1b-102">Метод IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="9bf1b-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="9bf1b-103">Возвращает значение, указывающее, помечена ли указанный токен метаданных обработки.</span><span class="sxs-lookup"><span data-stu-id="9bf1b-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bf1b-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bf1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bf1b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9bf1b-106">[in] Токен для проверки для обработки знака.</span><span class="sxs-lookup"><span data-stu-id="9bf1b-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="9bf1b-107">[out] Значение, которое является `true` Если `tk` была обработана; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9bf1b-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf1b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9bf1b-108">Requirements</span></span>  
 <span data-ttu-id="9bf1b-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bf1b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf1b-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9bf1b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9bf1b-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9bf1b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9bf1b-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf1b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf1b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="9bf1b-113">See Also</span></span>  
 [<span data-ttu-id="9bf1b-114">Imetadatafilter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9bf1b-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
