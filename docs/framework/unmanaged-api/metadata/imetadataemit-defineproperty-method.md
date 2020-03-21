---
title: Метод IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175789"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="65316-102">Метод IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="65316-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="65316-103">Создает определение свойства для указанного типа `get` `set` с указанными и доступными для метода, и получает маркер к определению этого свойства.</span><span class="sxs-lookup"><span data-stu-id="65316-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65316-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65316-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65316-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65316-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="65316-106">(в) Токен для класса или интерфейса, на котором определяется свойство.</span><span class="sxs-lookup"><span data-stu-id="65316-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="65316-107">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="65316-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="65316-108">(в) Флаги свойств.</span><span class="sxs-lookup"><span data-stu-id="65316-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="65316-109">(в) Подпись собственности.</span><span class="sxs-lookup"><span data-stu-id="65316-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="65316-110">(в) Количество байтов `pvSig`в .</span><span class="sxs-lookup"><span data-stu-id="65316-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="65316-111">(в) Тип значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65316-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="65316-112">(в) Значение значения по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="65316-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="65316-113">(в) Количество символов (Unicode) `pValue`в .</span><span class="sxs-lookup"><span data-stu-id="65316-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="65316-114">(в) Метод, устанавливающие значение свойства.</span><span class="sxs-lookup"><span data-stu-id="65316-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="65316-115">(в) Метод, который получает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="65316-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="65316-116">(в) Массив других методов, связанных с свойством.</span><span class="sxs-lookup"><span data-stu-id="65316-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="65316-117">Упраздните `mdTokenNil`массив с помощью .</span><span class="sxs-lookup"><span data-stu-id="65316-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="65316-118">(ваут) Назначенный `mdProperty` маркер.</span><span class="sxs-lookup"><span data-stu-id="65316-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65316-119">Требования</span><span class="sxs-lookup"><span data-stu-id="65316-119">Requirements</span></span>  
 <span data-ttu-id="65316-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65316-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65316-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65316-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65316-122">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65316-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65316-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65316-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65316-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65316-124">See also</span></span>

- [<span data-ttu-id="65316-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="65316-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="65316-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="65316-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
