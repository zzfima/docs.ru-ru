---
title: Метод IMetaDataImport::EnumFieldsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: bb8b531a884c9d3c2f33aa4aec5c4dbeaafe2b66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177344"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="04d32-102">Метод IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="04d32-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="04d32-103">Перечисляет токены FieldDef заданного типа с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="04d32-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04d32-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04d32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04d32-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="04d32-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="04d32-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="04d32-107">(в) Токен типа, поля которого должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="04d32-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="04d32-108">(в) Имя поля, ограничивающее область перечисления.</span><span class="sxs-lookup"><span data-stu-id="04d32-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="04d32-109">(ваут) Array используется для хранения токенов FieldDef.</span><span class="sxs-lookup"><span data-stu-id="04d32-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="04d32-110">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="04d32-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="04d32-111">(ваут) Фактическое количество токенов FieldDef `rFields`вернулось в .</span><span class="sxs-lookup"><span data-stu-id="04d32-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04d32-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="04d32-112">Remarks</span></span>  
 <span data-ttu-id="04d32-113">В отличие от [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` отбрасывает все токены поля, которые не имеют указанного имени.</span><span class="sxs-lookup"><span data-stu-id="04d32-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04d32-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="04d32-114">Return Value</span></span>  
  
|<span data-ttu-id="04d32-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04d32-115">HRESULT</span></span>|<span data-ttu-id="04d32-116">Описание</span><span class="sxs-lookup"><span data-stu-id="04d32-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="04d32-117">`EnumFieldsWithName`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="04d32-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="04d32-118">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="04d32-118">There are no fields to enumerate.</span></span> <span data-ttu-id="04d32-119">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="04d32-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04d32-120">Требования</span><span class="sxs-lookup"><span data-stu-id="04d32-120">Requirements</span></span>  
 <span data-ttu-id="04d32-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04d32-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d32-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04d32-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04d32-123">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04d32-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04d32-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d32-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d32-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="04d32-125">See also</span></span>

- [<span data-ttu-id="04d32-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="04d32-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="04d32-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="04d32-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
