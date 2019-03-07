---
title: Метод IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96f0b1648c8182b4d075a479f9bd376dbe33ef61
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487915"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="7c99f-102">Метод IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="7c99f-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="7c99f-103">Указывает, что будет обрабатываться заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="7c99f-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c99f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c99f-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c99f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7c99f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7c99f-106">[in] Токен метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="7c99f-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c99f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7c99f-107">Remarks</span></span>  
 <span data-ttu-id="7c99f-108">Как правило требуется токен обработать, если он находится в области метаданных.</span><span class="sxs-lookup"><span data-stu-id="7c99f-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="7c99f-109">`MarkToken` Методу передается в обработчик метаданных через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7c99f-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c99f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7c99f-110">Requirements</span></span>  
 <span data-ttu-id="7c99f-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c99f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c99f-112">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c99f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c99f-113">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c99f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c99f-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c99f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c99f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7c99f-115">See also</span></span>
- [<span data-ttu-id="7c99f-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="7c99f-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="7c99f-117">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="7c99f-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
