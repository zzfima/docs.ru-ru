---
title: "Метод IMetaDataEmit::DefineUserString"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 729f2d48722fb34b844636b416edf36d715e1a48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="a71eb-102">Метод IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="a71eb-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="a71eb-103">Получает маркер метаданных для заданной строки литерала.</span><span class="sxs-lookup"><span data-stu-id="a71eb-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a71eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a71eb-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a71eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a71eb-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="a71eb-106">[in] Строка пользовательского для хранения.</span><span class="sxs-lookup"><span data-stu-id="a71eb-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="a71eb-107">[in] Число расширенных символов в `szString`.</span><span class="sxs-lookup"><span data-stu-id="a71eb-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="a71eb-108">[out] В назначенный лексема строки.</span><span class="sxs-lookup"><span data-stu-id="a71eb-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a71eb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a71eb-109">Requirements</span></span>  
 <span data-ttu-id="a71eb-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a71eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a71eb-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a71eb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a71eb-112">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a71eb-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a71eb-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a71eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a71eb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a71eb-114">See Also</span></span>  
 [<span data-ttu-id="a71eb-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a71eb-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a71eb-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a71eb-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
