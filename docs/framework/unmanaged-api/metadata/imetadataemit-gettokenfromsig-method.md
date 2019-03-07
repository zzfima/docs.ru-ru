---
title: Метод IMetaDataEmit::GetTokenFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f94c12654626e149b0f75327e8fdfa55aefe697
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467129"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="bd3ae-102">Метод IMetaDataEmit::GetTokenFromSig</span><span class="sxs-lookup"><span data-stu-id="bd3ae-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="bd3ae-103">Получает токен для заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="bd3ae-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd3ae-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd3ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd3ae-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="bd3ae-106">[in] Сигнатура сохраняется и сохраняется.</span><span class="sxs-lookup"><span data-stu-id="bd3ae-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="bd3ae-107">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="bd3ae-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="bd3ae-108">[out] `mdSignature` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="bd3ae-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd3ae-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bd3ae-109">Requirements</span></span>  
 <span data-ttu-id="bd3ae-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd3ae-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd3ae-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd3ae-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd3ae-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd3ae-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd3ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3ae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bd3ae-114">See also</span></span>
- [<span data-ttu-id="bd3ae-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bd3ae-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bd3ae-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bd3ae-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
