---
title: "Метод IMetaDataImport::EnumFieldsWithName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77b5ba7e191d9aa0f1587e4ac1ec25e655c27b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="10ab7-102">Метод IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="10ab7-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="10ab7-103">Перечисляет токены FieldDef заданного типа с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="10ab7-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ab7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10ab7-104">Syntax</span></span>  
  
```  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]  mdTypeDef       cl,   
   [in]  LPCWSTR         szName,   
   [out] mdFieldDef      rFields[],   
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTokens   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10ab7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10ab7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="10ab7-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="10ab7-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="10ab7-107">[in] Токен типа, поля которого предназначены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="10ab7-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="10ab7-108">[in] Имя поля, которое ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="10ab7-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="10ab7-109">[out] Массив, используемый для хранения токены FieldDef.</span><span class="sxs-lookup"><span data-stu-id="10ab7-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="10ab7-110">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="10ab7-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="10ab7-111">[out] Фактическое число возвращенных в токены FieldDef `rFields`.</span><span class="sxs-lookup"><span data-stu-id="10ab7-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10ab7-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="10ab7-112">Remarks</span></span>  
 <span data-ttu-id="10ab7-113">В отличие от [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` отменяет все маркеры поля, которые имеют указанное имя.</span><span class="sxs-lookup"><span data-stu-id="10ab7-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10ab7-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10ab7-114">Return Value</span></span>  
  
|<span data-ttu-id="10ab7-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10ab7-115">HRESULT</span></span>|<span data-ttu-id="10ab7-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="10ab7-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="10ab7-117">`EnumFieldsWithName`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="10ab7-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="10ab7-118">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="10ab7-118">There are no fields to enumerate.</span></span> <span data-ttu-id="10ab7-119">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="10ab7-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10ab7-120">Требования</span><span class="sxs-lookup"><span data-stu-id="10ab7-120">Requirements</span></span>  
 <span data-ttu-id="10ab7-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ab7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ab7-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="10ab7-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10ab7-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10ab7-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10ab7-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ab7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ab7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="10ab7-125">See Also</span></span>  
 [<span data-ttu-id="10ab7-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="10ab7-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="10ab7-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="10ab7-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
