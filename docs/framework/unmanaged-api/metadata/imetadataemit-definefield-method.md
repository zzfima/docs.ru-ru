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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8ba8a762c56a666c67b25b9ce0420099fce419a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044165"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="e948c-102">Метод IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="e948c-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="e948c-103">Создает определение для поля с заданной подписью метаданных и получает маркер для этого определения поля.</span><span class="sxs-lookup"><span data-stu-id="e948c-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e948c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e948c-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="e948c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e948c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e948c-106">[in] `mdTypeDef` Маркеров для включающего класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e948c-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="e948c-107">[in] Имя поля в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="e948c-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="e948c-108">[in] Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="e948c-108">[in] The field attributes.</span></span> <span data-ttu-id="e948c-109">Это битовая маска `CorFieldAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="e948c-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e948c-110">[in] Подпись поля как большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="e948c-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e948c-111">[in] Число байт в `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e948c-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="e948c-112">[in] `ELEMENT_TYPE_` *\** Для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="e948c-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="e948c-113">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="e948c-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="e948c-114">Если не применяется частное определение постоянное значение для поля, используйте `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="e948c-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="e948c-115">[in] Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="e948c-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="e948c-116">[in] Размер в символах (Юникод) `pValue`.</span><span class="sxs-lookup"><span data-stu-id="e948c-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="e948c-117">[out] `mdFieldDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="e948c-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e948c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e948c-118">Requirements</span></span>  
 <span data-ttu-id="e948c-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e948c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e948c-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e948c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e948c-121">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e948c-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e948c-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e948c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e948c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e948c-123">See also</span></span>

- [<span data-ttu-id="e948c-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e948c-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e948c-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e948c-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
