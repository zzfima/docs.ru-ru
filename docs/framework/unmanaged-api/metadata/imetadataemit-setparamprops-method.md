---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177496"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="31a53-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="31a53-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="31a53-103">Устанавливает или изменяет особенности параметра метода, который был определен предыдущим вызовом [на IMetaDataEmit::DefineParam.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)</span><span class="sxs-lookup"><span data-stu-id="31a53-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a53-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31a53-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31a53-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="31a53-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="31a53-106">(в) Токен для целевого параметра.</span><span class="sxs-lookup"><span data-stu-id="31a53-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="31a53-107">(в) Название параметра в Unicode.</span><span class="sxs-lookup"><span data-stu-id="31a53-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="31a53-108">(в) Флаги для параметра.</span><span class="sxs-lookup"><span data-stu-id="31a53-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="31a53-109">(в) За постоянную стоимость ELEMENT_TYPE_.</span><span class="sxs-lookup"><span data-stu-id="31a53-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="31a53-110">(в) Постоянное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="31a53-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="31a53-111">(в) Размер в (Unicode) символы `pValue`.</span><span class="sxs-lookup"><span data-stu-id="31a53-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31a53-112">Требования</span><span class="sxs-lookup"><span data-stu-id="31a53-112">Requirements</span></span>  
 <span data-ttu-id="31a53-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a53-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a53-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31a53-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31a53-115">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31a53-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31a53-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31a53-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31a53-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="31a53-117">See also</span></span>

- [<span data-ttu-id="31a53-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="31a53-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="31a53-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="31a53-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
