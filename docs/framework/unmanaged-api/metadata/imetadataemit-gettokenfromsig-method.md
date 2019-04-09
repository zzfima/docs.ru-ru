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
ms.openlocfilehash: 242618fb2a5ab748132baf68e24240d1ffaf2301
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139845"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="fbf87-102">Метод IMetaDataEmit::GetTokenFromSig</span><span class="sxs-lookup"><span data-stu-id="fbf87-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="fbf87-103">Получает токен для заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="fbf87-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf87-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbf87-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbf87-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbf87-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="fbf87-106">[in] Сигнатура сохраняется и сохраняется.</span><span class="sxs-lookup"><span data-stu-id="fbf87-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="fbf87-107">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="fbf87-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="fbf87-108">[out] `mdSignature` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="fbf87-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf87-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fbf87-109">Requirements</span></span>  
 <span data-ttu-id="fbf87-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbf87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf87-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fbf87-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbf87-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbf87-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fbf87-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fbf87-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbf87-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fbf87-114">See also</span></span>

- [<span data-ttu-id="fbf87-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="fbf87-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fbf87-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="fbf87-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
