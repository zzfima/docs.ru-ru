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
ms.openlocfilehash: b0b7d0364b6f58579ee8573d168d6c8180ac9dff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="b8318-102">Метод IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="b8318-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="b8318-103">Получает маркер метаданных для типа с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="b8318-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8318-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8318-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8318-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8318-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="b8318-106">[in] Сигнатура в процессе определения.</span><span class="sxs-lookup"><span data-stu-id="b8318-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="b8318-107">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="b8318-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="b8318-108">[out] `mdTypeSpec` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="b8318-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8318-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8318-109">Requirements</span></span>  
 <span data-ttu-id="b8318-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8318-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8318-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b8318-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8318-112">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8318-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8318-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8318-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8318-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b8318-114">See Also</span></span>  
 [<span data-ttu-id="b8318-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b8318-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b8318-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b8318-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
