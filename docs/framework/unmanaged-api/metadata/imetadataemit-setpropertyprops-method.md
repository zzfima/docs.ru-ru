---
title: Метод IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: dc6375f3e2cff1a744a8ff2e6a6adab27bbf8af3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177476"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="723cf-102">Метод IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="723cf-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="723cf-103">Устанавливает функции, хранящиеся в метаданных, для свойства, определяемого предыдущим вызовом [методу DefineProperty.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)</span><span class="sxs-lookup"><span data-stu-id="723cf-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="723cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="723cf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="723cf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="723cf-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="723cf-106">(в) Токен для изменения свойства</span><span class="sxs-lookup"><span data-stu-id="723cf-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="723cf-107">(в) Флаги свойств.</span><span class="sxs-lookup"><span data-stu-id="723cf-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="723cf-108">(в) Тип значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="723cf-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="723cf-109">(в) Значение значения по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="723cf-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="723cf-110">(в) Количество символов (Unicode) `pValue`в .</span><span class="sxs-lookup"><span data-stu-id="723cf-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="723cf-111">(в) Метод, устанавливающие значение свойства.</span><span class="sxs-lookup"><span data-stu-id="723cf-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="723cf-112">(в) Метод, который получает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="723cf-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="723cf-113">(в) Массив других методов, связанных с свойством.</span><span class="sxs-lookup"><span data-stu-id="723cf-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="723cf-114">Прекратите этот `mdTokenNil` массив с помощью маркера.</span><span class="sxs-lookup"><span data-stu-id="723cf-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="723cf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="723cf-115">Requirements</span></span>  
 <span data-ttu-id="723cf-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="723cf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="723cf-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="723cf-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="723cf-118">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="723cf-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="723cf-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="723cf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723cf-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="723cf-120">See also</span></span>

- [<span data-ttu-id="723cf-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="723cf-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="723cf-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="723cf-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
