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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ed8bbbd9699fe707d638bb8d07064e508b6f2fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447776"
---
# <a name="imetadataimportenumfieldswithname-method"></a><span data-ttu-id="85d16-102">Метод IMetaDataImport::EnumFieldsWithName</span><span class="sxs-lookup"><span data-stu-id="85d16-102">IMetaDataImport::EnumFieldsWithName Method</span></span>
<span data-ttu-id="85d16-103">Перечисляет токены FieldDef заданного типа с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="85d16-103">Enumerates FieldDef tokens of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85d16-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85d16-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="85d16-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85d16-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="85d16-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="85d16-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="85d16-107">[in] Токен типа, поля которого предназначены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="85d16-107">[in] The token of the type whose fields are to be enumerated.</span></span>  
  
 `szName`  
 <span data-ttu-id="85d16-108">[in] Имя поля, которое ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="85d16-108">[in] The field name that limits the scope of the enumeration.</span></span>  
  
 `rFields`  
 <span data-ttu-id="85d16-109">[out] Массив, используемый для хранения токены FieldDef.</span><span class="sxs-lookup"><span data-stu-id="85d16-109">[out] Array used to store the FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="85d16-110">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="85d16-110">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="85d16-111">[out] Фактическое число возвращенных в токены FieldDef `rFields`.</span><span class="sxs-lookup"><span data-stu-id="85d16-111">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85d16-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="85d16-112">Remarks</span></span>  
 <span data-ttu-id="85d16-113">В отличие от [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` отменяет все маркеры поля, которые имеют указанное имя.</span><span class="sxs-lookup"><span data-stu-id="85d16-113">Unlike [IMetaDataImport::EnumFields](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md), `EnumFieldsWithName` discards all field tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85d16-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="85d16-114">Return Value</span></span>  
  
|<span data-ttu-id="85d16-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85d16-115">HRESULT</span></span>|<span data-ttu-id="85d16-116">Описание</span><span class="sxs-lookup"><span data-stu-id="85d16-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="85d16-117">`EnumFieldsWithName` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="85d16-117">`EnumFieldsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="85d16-118">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="85d16-118">There are no fields to enumerate.</span></span> <span data-ttu-id="85d16-119">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="85d16-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85d16-120">Требования</span><span class="sxs-lookup"><span data-stu-id="85d16-120">Requirements</span></span>  
 <span data-ttu-id="85d16-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85d16-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85d16-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85d16-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85d16-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85d16-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85d16-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85d16-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d16-125">См. также</span><span class="sxs-lookup"><span data-stu-id="85d16-125">See Also</span></span>  
 [<span data-ttu-id="85d16-126">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="85d16-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="85d16-127">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="85d16-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
