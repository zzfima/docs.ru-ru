---
title: Метод IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177704"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="4ab4b-102">Метод IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="4ab4b-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="4ab4b-103">Создает определение для поля с указанной подписью метаданных и получает маркер в этом определении поля.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab4b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ab4b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ab4b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ab4b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4ab4b-106">(в) Токен `mdTypeDef` для прилагающего класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="4ab4b-107">(в) Название поля в Unicode.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="4ab4b-108">(в) Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-108">[in] The field attributes.</span></span> <span data-ttu-id="4ab4b-109">Это битмаска ценностей. `CorFieldAttr`</span><span class="sxs-lookup"><span data-stu-id="4ab4b-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4ab4b-110">(в) Подпись поля как BLOB.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4ab4b-111">(в) Количество байтов `pvSigBlob`в .</span><span class="sxs-lookup"><span data-stu-id="4ab4b-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4ab4b-112">(в) Для `ELEMENT_TYPE_` *\** постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="4ab4b-113">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="4ab4b-114">Если не определить постоянное значение `ELEMENT_TYPE_END`для поля, используйте .</span><span class="sxs-lookup"><span data-stu-id="4ab4b-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4ab4b-115">(в) Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4ab4b-116">(в) Размер в (Unicode) символы `pValue`.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="4ab4b-117">(ваут) Назначенный `mdFieldDef` маркер.</span><span class="sxs-lookup"><span data-stu-id="4ab4b-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab4b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4ab4b-118">Requirements</span></span>  
 <span data-ttu-id="4ab4b-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ab4b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab4b-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ab4b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ab4b-121">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ab4b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ab4b-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab4b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab4b-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4ab4b-123">See also</span></span>

- [<span data-ttu-id="4ab4b-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4ab4b-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4ab4b-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4ab4b-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
