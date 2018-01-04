---
title: "Метод IMetaDataDispenserEx::FindAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f125008e4ae5b7f2abbe6d467b486b962700d42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="45f79-102">Метод IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="45f79-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="45f79-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="45f79-103">This method is not implemented.</span></span> <span data-ttu-id="45f79-104">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="45f79-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f79-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45f79-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45f79-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="45f79-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="45f79-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="45f79-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="45f79-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="45f79-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="45f79-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="45f79-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="45f79-110">[in] Сборки, который требуется найти.</span><span class="sxs-lookup"><span data-stu-id="45f79-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="45f79-111">[out] Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="45f79-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="45f79-112">[in] Размер в байтах для `szName`.</span><span class="sxs-lookup"><span data-stu-id="45f79-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="45f79-113">[out] Число символов, фактически извлеченных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="45f79-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45f79-114">Требования</span><span class="sxs-lookup"><span data-stu-id="45f79-114">Requirements</span></span>  
 <span data-ttu-id="45f79-115">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45f79-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45f79-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45f79-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45f79-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45f79-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45f79-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45f79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f79-119">См. также</span><span class="sxs-lookup"><span data-stu-id="45f79-119">See Also</span></span>  
 [<span data-ttu-id="45f79-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="45f79-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="45f79-121">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="45f79-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
