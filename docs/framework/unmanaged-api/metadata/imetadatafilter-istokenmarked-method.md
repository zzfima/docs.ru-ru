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
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177380"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="88758-102">Метод IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="88758-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="88758-103">Получает значение, указывающее, был ли указанный токен метаданных помечен как обработанный.</span><span class="sxs-lookup"><span data-stu-id="88758-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88758-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88758-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88758-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88758-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="88758-106">(в) Токен для изучения для обрабатывающего знака.</span><span class="sxs-lookup"><span data-stu-id="88758-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="88758-107">(ваут) Значение, если `true` `tk` обработано; в `false`противном случае .</span><span class="sxs-lookup"><span data-stu-id="88758-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88758-108">Требования</span><span class="sxs-lookup"><span data-stu-id="88758-108">Requirements</span></span>  
 <span data-ttu-id="88758-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88758-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88758-110">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88758-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88758-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88758-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88758-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88758-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88758-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="88758-113">See also</span></span>

- [<span data-ttu-id="88758-114">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="88758-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
