---
title: Метод IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2509945d2799b81e036888d146a51cee87fda09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169849"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="94545-102">Метод IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="94545-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="94545-103">Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="94545-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94545-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94545-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94545-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94545-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="94545-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="94545-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="94545-107">[in] Токен TypeDef, представляющий тип с члены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="94545-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="94545-108">[in] Имя члена, который ограничивает область перечислителя.</span><span class="sxs-lookup"><span data-stu-id="94545-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="94545-109">[out] Массив, используемый для хранения токенов MemberDef.</span><span class="sxs-lookup"><span data-stu-id="94545-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="94545-110">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="94545-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="94545-111">[out] Фактическое количество возвращаемых в токены MemberDef `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="94545-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94545-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="94545-112">Remarks</span></span>  
 <span data-ttu-id="94545-113">Этот метод перечисляет поля и методы, но не свойства или события.</span><span class="sxs-lookup"><span data-stu-id="94545-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="94545-114">В отличие от [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` отбрасывает все поля и элемент маркеры, у которых нет указанного имени.</span><span class="sxs-lookup"><span data-stu-id="94545-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94545-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="94545-115">Return Value</span></span>  
  
|<span data-ttu-id="94545-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94545-116">HRESULT</span></span>|<span data-ttu-id="94545-117">Описание</span><span class="sxs-lookup"><span data-stu-id="94545-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="94545-118">`EnumTypeDefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="94545-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="94545-119">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="94545-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="94545-120">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="94545-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94545-121">Требования</span><span class="sxs-lookup"><span data-stu-id="94545-121">Requirements</span></span>  
 <span data-ttu-id="94545-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94545-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94545-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94545-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94545-124">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94545-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94545-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94545-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94545-126">См. также</span><span class="sxs-lookup"><span data-stu-id="94545-126">See also</span></span>

- [<span data-ttu-id="94545-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="94545-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="94545-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="94545-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
