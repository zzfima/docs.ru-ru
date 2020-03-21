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
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177410"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="7e5b4-102">Метод IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="7e5b4-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="7e5b4-103">Устанавливает значения свойств для общего определения параметров, на который ссылается указанный маркер.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e5b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e5b4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e5b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e5b4-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="7e5b4-106">(в) Токен для общего определения параметров, для которого можно установить значения.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="7e5b4-107">(в) Значение перечисления [CorGenericParamAttr,](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) описывающий тип для общего параметра.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e5b4-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-108">[in] Optional.</span></span> <span data-ttu-id="7e5b4-109">Название параметра, для которого можно установить значения.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="7e5b4-110">(в) Зарезервировано для будущей расширяемости.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="7e5b4-111">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-111">[in] Optional.</span></span> <span data-ttu-id="7e5b4-112">Нулевой уровень ограничений типа.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="7e5b4-113">Члены массива `mdTypeDef` `mdTypeRef`должны `mdTypeSpec` быть токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="7e5b4-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e5b4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7e5b4-114">Requirements</span></span>  
 <span data-ttu-id="7e5b4-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e5b4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e5b4-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7e5b4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e5b4-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e5b4-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e5b4-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e5b4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5b4-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7e5b4-119">See also</span></span>

- [<span data-ttu-id="7e5b4-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7e5b4-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="7e5b4-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7e5b4-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
