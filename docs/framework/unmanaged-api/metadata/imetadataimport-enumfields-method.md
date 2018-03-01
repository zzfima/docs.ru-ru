---
title: "Метод IMetaDataImport::EnumFields"
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
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1a4548494ffd766cbf10558121f5c2df6cf63cba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="a8bf5-102">Метод IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="a8bf5-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="a8bf5-103">Перечисляет токены FieldDef для типа, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8bf5-104">Syntax</span></span>  
  
```  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8bf5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a8bf5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a8bf5-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="a8bf5-107">[in] Токен TypeDef класса, поля которого предназначены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="a8bf5-108">[out] Список токены FieldDef.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a8bf5-109">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a8bf5-110">[out] Фактическое число возвращенных в токены FieldDef `rFields`.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8bf5-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a8bf5-111">Return Value</span></span>  
  
|<span data-ttu-id="a8bf5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8bf5-112">HRESULT</span></span>|<span data-ttu-id="a8bf5-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="a8bf5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a8bf5-114">`EnumFields`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a8bf5-115">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-115">There are no fields to enumerate.</span></span> <span data-ttu-id="a8bf5-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a8bf5-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8bf5-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a8bf5-117">Requirements</span></span>  
 <span data-ttu-id="a8bf5-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bf5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bf5-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8bf5-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8bf5-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8bf5-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8bf5-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bf5-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bf5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a8bf5-122">See Also</span></span>  
 [<span data-ttu-id="a8bf5-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a8bf5-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a8bf5-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a8bf5-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
