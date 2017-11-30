---
title: "Метод IMetaDataEmit::GetTokenFromTypeSpec"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetTokenFromTypeSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f83d1adb37691b525927eeb8a87b620fa3c7353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="8e997-102">Метод IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="8e997-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="8e997-103">Получает маркер метаданных для типа с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="8e997-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e997-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e997-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e997-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e997-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="8e997-106">[in] Сигнатура в процессе определения.</span><span class="sxs-lookup"><span data-stu-id="8e997-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="8e997-107">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="8e997-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="8e997-108">[out] `mdTypeSpec` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="8e997-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e997-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8e997-109">Requirements</span></span>  
 <span data-ttu-id="8e997-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e997-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e997-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8e997-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e997-112">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e997-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e997-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e997-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e997-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8e997-114">See Also</span></span>  
 [<span data-ttu-id="8e997-115">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8e997-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8e997-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8e997-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
