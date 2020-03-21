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
ms.openlocfilehash: 7410f91a853f3a677a105dc2e12a86d723c9fad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177322"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="77140-102">Метод IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="77140-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="77140-103">Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="77140-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77140-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77140-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77140-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77140-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="77140-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="77140-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="77140-107">(в) Токен TypeDef, представляющий тип с членами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="77140-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="77140-108">(в) Имя участника, ограничивающее область охвата регистратора.</span><span class="sxs-lookup"><span data-stu-id="77140-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="77140-109">(ваут) Массив, используемый для хранения токенов MemberDef.</span><span class="sxs-lookup"><span data-stu-id="77140-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="77140-110">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="77140-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="77140-111">(ваут) Фактическое количество токенов MemberDef `rMembers`возвращено в .</span><span class="sxs-lookup"><span data-stu-id="77140-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77140-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="77140-112">Remarks</span></span>  
 <span data-ttu-id="77140-113">Этот метод перечисляет поля и методы, но не свойства или события.</span><span class="sxs-lookup"><span data-stu-id="77140-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="77140-114">В отличие от [IMetaDataImport::EnumMembers,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md) `EnumMembersWithName` отбрасываются все поля и токены-члены, которые не имеют указанного имени.</span><span class="sxs-lookup"><span data-stu-id="77140-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77140-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="77140-115">Return Value</span></span>  
  
|<span data-ttu-id="77140-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77140-116">HRESULT</span></span>|<span data-ttu-id="77140-117">Описание</span><span class="sxs-lookup"><span data-stu-id="77140-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="77140-118">`EnumTypeDefs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="77140-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="77140-119">Нет токенов MemberDef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="77140-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="77140-120">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="77140-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77140-121">Требования</span><span class="sxs-lookup"><span data-stu-id="77140-121">Requirements</span></span>  
 <span data-ttu-id="77140-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77140-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77140-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77140-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77140-124">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77140-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77140-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77140-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77140-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="77140-126">See also</span></span>

- [<span data-ttu-id="77140-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="77140-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="77140-128">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="77140-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
