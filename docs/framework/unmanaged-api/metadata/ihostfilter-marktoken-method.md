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
ms.openlocfilehash: 52375486eb9d7780a51808dedc5f876587efb115
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444568"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="0a21c-102">Метод IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="0a21c-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="0a21c-103">Указывает, что будет обрабатываться заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a21c-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a21c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a21c-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a21c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a21c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0a21c-106">[in] Токен метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="0a21c-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a21c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a21c-107">Remarks</span></span>  
 <span data-ttu-id="0a21c-108">Как правило требуется маркер для обработки, если он находится в области метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a21c-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="0a21c-109">`MarkToken` Методу передается в ядро метаданных через [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0a21c-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a21c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0a21c-110">Requirements</span></span>  
 <span data-ttu-id="0a21c-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a21c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a21c-112">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a21c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a21c-113">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a21c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a21c-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a21c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a21c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0a21c-115">See Also</span></span>  
 [<span data-ttu-id="0a21c-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="0a21c-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="0a21c-117">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="0a21c-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
