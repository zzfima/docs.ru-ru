---
title: "Метод IMetaDataEmit2::SetGenericParamProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8e0720934fa9d7ec3669fa1cef7ac3ef9aedaa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="7e0da-102">Метод IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="7e0da-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="7e0da-103">Задает значения свойств для определения универсальных параметров, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="7e0da-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e0da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e0da-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e0da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e0da-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="7e0da-106">[in] Токен для определения универсальных параметров, для которого требуется задать значения.</span><span class="sxs-lookup"><span data-stu-id="7e0da-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="7e0da-107">[in] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее тип универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="7e0da-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e0da-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e0da-108">[in] Optional.</span></span> <span data-ttu-id="7e0da-109">Имя параметра, для которого требуется задать значения.</span><span class="sxs-lookup"><span data-stu-id="7e0da-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="7e0da-110">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="7e0da-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="7e0da-111">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e0da-111">[in] Optional.</span></span> <span data-ttu-id="7e0da-112">Нулем массив ограничения типа.</span><span class="sxs-lookup"><span data-stu-id="7e0da-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="7e0da-113">Элементы массива должны быть `mdTypeDef`, `mdTypeRef`, или `mdTypeSpec` токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="7e0da-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e0da-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7e0da-114">Requirements</span></span>  
 <span data-ttu-id="7e0da-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e0da-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e0da-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e0da-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e0da-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e0da-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e0da-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e0da-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e0da-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7e0da-119">See Also</span></span>  
 [<span data-ttu-id="7e0da-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7e0da-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="7e0da-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7e0da-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
