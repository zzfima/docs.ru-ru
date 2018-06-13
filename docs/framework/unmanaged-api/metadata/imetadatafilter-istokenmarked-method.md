---
title: Метод IMetaDataFilter::IsTokenMarked
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bf5149e8e42a810a6a490767638b374f66b5679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445868"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="c1662-102">Метод IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="c1662-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="c1662-103">Возвращает значение, указывающее, помечена ли указанный токен метаданных обработки.</span><span class="sxs-lookup"><span data-stu-id="c1662-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1662-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1662-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1662-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1662-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c1662-106">[in] Токен для проверки для обработки знака.</span><span class="sxs-lookup"><span data-stu-id="c1662-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="c1662-107">[out] Значение, которое является `true` Если `tk` была обработана; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="c1662-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1662-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c1662-108">Requirements</span></span>  
 <span data-ttu-id="c1662-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1662-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1662-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1662-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1662-111">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1662-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1662-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1662-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1662-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c1662-113">See Also</span></span>  
 [<span data-ttu-id="c1662-114">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="c1662-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
