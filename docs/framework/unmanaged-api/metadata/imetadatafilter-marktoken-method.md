---
title: Метод IMetaDataFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f184bae4628f2aa357644188594396468671ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444156"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="b0b87-102">Метод IMetaDataFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="b0b87-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="b0b87-103">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="b0b87-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0b87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0b87-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0b87-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0b87-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b0b87-106">[in] Токен для пометки сразу после обработки.</span><span class="sxs-lookup"><span data-stu-id="b0b87-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0b87-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b0b87-107">Requirements</span></span>  
 <span data-ttu-id="b0b87-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0b87-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0b87-109">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b0b87-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b0b87-110">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0b87-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b0b87-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0b87-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b87-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b0b87-112">See Also</span></span>  
 [<span data-ttu-id="b0b87-113">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="b0b87-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
