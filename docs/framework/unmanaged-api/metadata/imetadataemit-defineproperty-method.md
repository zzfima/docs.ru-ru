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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69b398fa003abc0dba00ee89a9bb911a8c2dd6df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777516"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="64280-102">Метод IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="64280-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="64280-103">Создает определение свойства для указанного типа с заданным `get` и `set` метод доступа и получает маркер для этого определения свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64280-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64280-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="64280-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64280-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="64280-106">[in] Токен для класса или интерфейса, на котором определено свойство.</span><span class="sxs-lookup"><span data-stu-id="64280-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="64280-107">[in] Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="64280-108">[in] Флаги свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="64280-109">[in] Сигнатура свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="64280-110">[in] Число байт в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="64280-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="64280-111">[in] Тип значения свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64280-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="64280-112">[in] Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="64280-113">[in] Количество (Юникод) символы в `pValue`.</span><span class="sxs-lookup"><span data-stu-id="64280-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="64280-114">[in] Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="64280-115">[in] Метод, который возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="64280-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="64280-116">[in] Массив, другие методы, связанные со свойством.</span><span class="sxs-lookup"><span data-stu-id="64280-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="64280-117">Массива с `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="64280-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="64280-118">[out] `mdProperty` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="64280-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64280-119">Требования</span><span class="sxs-lookup"><span data-stu-id="64280-119">Requirements</span></span>  
 <span data-ttu-id="64280-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64280-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64280-121">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64280-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64280-122">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64280-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64280-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64280-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64280-124">См. также</span><span class="sxs-lookup"><span data-stu-id="64280-124">See also</span></span>

- [<span data-ttu-id="64280-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="64280-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="64280-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="64280-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
