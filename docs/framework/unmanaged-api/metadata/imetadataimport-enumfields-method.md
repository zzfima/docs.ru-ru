---
title: Метод IMetaDataImport::EnumFields
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65f59d3df96f46ad65650183bdb6f631356a4d0b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775531"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="08452-102">Метод IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="08452-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="08452-103">Перечисляет токены FieldDef для типа, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="08452-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08452-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08452-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [out]     mdFieldDef  rFields[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08452-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08452-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="08452-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="08452-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="08452-107">[in] Токен TypeDef, поля которого предназначены для перечисления класса.</span><span class="sxs-lookup"><span data-stu-id="08452-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="08452-108">[out] Список токены FieldDef.</span><span class="sxs-lookup"><span data-stu-id="08452-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="08452-109">[in] Максимальный размер массива `rFields`.</span><span class="sxs-lookup"><span data-stu-id="08452-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="08452-110">[out] Фактическое количество возвращаемых в токены FieldDef `rFields`.</span><span class="sxs-lookup"><span data-stu-id="08452-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08452-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08452-111">Return Value</span></span>  
  
|<span data-ttu-id="08452-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08452-112">HRESULT</span></span>|<span data-ttu-id="08452-113">Описание</span><span class="sxs-lookup"><span data-stu-id="08452-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="08452-114">`EnumFields` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="08452-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="08452-115">Нет полей для перечисления.</span><span class="sxs-lookup"><span data-stu-id="08452-115">There are no fields to enumerate.</span></span> <span data-ttu-id="08452-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="08452-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08452-117">Требования</span><span class="sxs-lookup"><span data-stu-id="08452-117">Requirements</span></span>  
 <span data-ttu-id="08452-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08452-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08452-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08452-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08452-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08452-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08452-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08452-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08452-122">См. также</span><span class="sxs-lookup"><span data-stu-id="08452-122">See also</span></span>

- [<span data-ttu-id="08452-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08452-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="08452-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08452-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
