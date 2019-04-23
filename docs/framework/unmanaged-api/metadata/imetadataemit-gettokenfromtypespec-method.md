---
title: Метод IMetaDataEmit::GetTokenFromTypeSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09256deafdb42847f369664ec8c4bc96d72424d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177610"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="63f0e-102">Метод IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="63f0e-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="63f0e-103">Получает маркер метаданных для типа с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="63f0e-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63f0e-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63f0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="63f0e-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="63f0e-106">[in] Будучи определенным сигнатура.</span><span class="sxs-lookup"><span data-stu-id="63f0e-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="63f0e-107">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="63f0e-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="63f0e-108">[out] `mdTypeSpec` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="63f0e-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f0e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="63f0e-109">Requirements</span></span>  
 <span data-ttu-id="63f0e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f0e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f0e-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63f0e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63f0e-112">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="63f0e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63f0e-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f0e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f0e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="63f0e-114">See also</span></span>

- [<span data-ttu-id="63f0e-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="63f0e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="63f0e-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="63f0e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
