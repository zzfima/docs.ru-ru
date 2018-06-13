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
ms.openlocfilehash: e5fca698adc4d08d805fec2ff80af377366674b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445959"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="11e1e-102">Метод IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="11e1e-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="11e1e-103">Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="11e1e-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11e1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11e1e-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="11e1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11e1e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="11e1e-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="11e1e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="11e1e-107">[in] Токен TypeDef, представляющий тип с члены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="11e1e-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="11e1e-108">[in] Имя члена, который ограничивает область перечислителя.</span><span class="sxs-lookup"><span data-stu-id="11e1e-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="11e1e-109">[out] Массив, используемый для хранения MemberDef токенов.</span><span class="sxs-lookup"><span data-stu-id="11e1e-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="11e1e-110">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="11e1e-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="11e1e-111">[out] Фактическое число токены MemberDef, возвращаемых в `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="11e1e-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11e1e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="11e1e-112">Remarks</span></span>  
 <span data-ttu-id="11e1e-113">Этот метод перечисляет поля и методы, но не свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="11e1e-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="11e1e-114">В отличие от [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` отменяет все маркеры полей и элементов, которые имеют указанное имя.</span><span class="sxs-lookup"><span data-stu-id="11e1e-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11e1e-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11e1e-115">Return Value</span></span>  
  
|<span data-ttu-id="11e1e-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11e1e-116">HRESULT</span></span>|<span data-ttu-id="11e1e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="11e1e-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="11e1e-118">`EnumTypeDefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="11e1e-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="11e1e-119">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="11e1e-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="11e1e-120">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="11e1e-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11e1e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="11e1e-121">Requirements</span></span>  
 <span data-ttu-id="11e1e-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11e1e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11e1e-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11e1e-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11e1e-124">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11e1e-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11e1e-125">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11e1e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e1e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="11e1e-126">See Also</span></span>  
 [<span data-ttu-id="11e1e-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="11e1e-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="11e1e-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="11e1e-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
