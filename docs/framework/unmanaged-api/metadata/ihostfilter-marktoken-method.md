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
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432242"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="3abaf-102">Метод IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="3abaf-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="3abaf-103">Указывает, что заданный маркер метаданных будет обработан.</span><span class="sxs-lookup"><span data-stu-id="3abaf-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abaf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3abaf-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3abaf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3abaf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3abaf-106">окне Токен метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="3abaf-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3abaf-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="3abaf-107">Remarks</span></span>  
 <span data-ttu-id="3abaf-108">Как правило, требуется обработка маркера, если он находится в области действия метаданных.</span><span class="sxs-lookup"><span data-stu-id="3abaf-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="3abaf-109">Метод `MarkToken` передается в обработчик метаданных с помощью метода [IMetaDataEmit:: сесандлер](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3abaf-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abaf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3abaf-110">Requirements</span></span>  
 <span data-ttu-id="3abaf-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3abaf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3abaf-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3abaf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3abaf-113">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3abaf-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3abaf-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3abaf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abaf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3abaf-115">See also</span></span>

- [<span data-ttu-id="3abaf-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="3abaf-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="3abaf-117">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="3abaf-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
