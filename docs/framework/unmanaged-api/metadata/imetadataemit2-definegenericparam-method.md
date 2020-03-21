---
title: Метод IMetaDataEmit2::DefineGenericParam
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177445"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="ebef5-102">Метод IMetaDataEmit2::DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="ebef5-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="ebef5-103">Создает определение для общего параметра типа и получает маркер к этому общему параметру типа.</span><span class="sxs-lookup"><span data-stu-id="ebef5-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebef5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebef5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebef5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebef5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ebef5-106">(в) Символ `mdTypeDef` `mdMethodDef` или маркер, представляющий метод или конструктор для определения общего параметра.</span><span class="sxs-lookup"><span data-stu-id="ebef5-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="ebef5-107">(в) Индекс общего параметра.</span><span class="sxs-lookup"><span data-stu-id="ebef5-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="ebef5-108">(в) Значение перечисления [CorGenericParamAttr,](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) описывающий тип для общего параметра.</span><span class="sxs-lookup"><span data-stu-id="ebef5-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="ebef5-109">(в) Название параметра.</span><span class="sxs-lookup"><span data-stu-id="ebef5-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="ebef5-110">(в) Этот параметр зарезервирован для будущей расширяемости.</span><span class="sxs-lookup"><span data-stu-id="ebef5-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="ebef5-111">(в) Нулевой уровень ограничений типа.</span><span class="sxs-lookup"><span data-stu-id="ebef5-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="ebef5-112">Члены массива `mdTypeDef` `mdTypeRef`должны `mdTypeSpec` быть токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="ebef5-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="ebef5-113">(ваут) Токен, представляющий общий параметр.</span><span class="sxs-lookup"><span data-stu-id="ebef5-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebef5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ebef5-114">Requirements</span></span>  
 <span data-ttu-id="ebef5-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebef5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebef5-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ebef5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebef5-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebef5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ebef5-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebef5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebef5-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ebef5-119">See also</span></span>

- [<span data-ttu-id="ebef5-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ebef5-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ebef5-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ebef5-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
