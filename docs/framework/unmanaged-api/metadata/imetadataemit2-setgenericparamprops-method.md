---
title: Метод IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 406a8ea4600c1e5ef55c0d905ff3aa4a30d068e7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485217"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="f1e02-102">Метод IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="f1e02-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="f1e02-103">Задает значения свойств для определения универсального параметра, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="f1e02-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1e02-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1e02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1e02-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="f1e02-106">[in] Токен для определения универсальных параметров, для которого требуется задать значения.</span><span class="sxs-lookup"><span data-stu-id="f1e02-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="f1e02-107">[in] Значение [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) перечисление, описывающее тип универсального параметра.</span><span class="sxs-lookup"><span data-stu-id="f1e02-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="f1e02-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="f1e02-108">[in] Optional.</span></span> <span data-ttu-id="f1e02-109">Имя параметра, для которого требуется задать значения.</span><span class="sxs-lookup"><span data-stu-id="f1e02-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="f1e02-110">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="f1e02-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="f1e02-111">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="f1e02-111">[in] Optional.</span></span> <span data-ttu-id="f1e02-112">Массив типа ограничения, оканчивающаяся нулем.</span><span class="sxs-lookup"><span data-stu-id="f1e02-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="f1e02-113">Элементы массива должны быть `mdTypeDef`, `mdTypeRef`, или `mdTypeSpec` токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="f1e02-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1e02-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f1e02-114">Requirements</span></span>  
 <span data-ttu-id="f1e02-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1e02-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e02-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1e02-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1e02-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1e02-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1e02-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1e02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e02-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f1e02-119">See also</span></span>
- [<span data-ttu-id="f1e02-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f1e02-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="f1e02-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f1e02-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
