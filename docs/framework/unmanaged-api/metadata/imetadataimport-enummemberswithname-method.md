---
title: "Метод IMetaDataImport::EnumMembersWithName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembersWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64568fb185cd8a18e43639568ecb67fcfa350dba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="d5d68-102">Метод IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="d5d68-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="d5d68-103">Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="d5d68-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d68-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5d68-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="d5d68-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5d68-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d5d68-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="d5d68-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d5d68-107">[in] Токен TypeDef, представляющий тип с члены для перечисления.</span><span class="sxs-lookup"><span data-stu-id="d5d68-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5d68-108">[in] Имя члена, который ограничивает область перечислителя.</span><span class="sxs-lookup"><span data-stu-id="d5d68-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="d5d68-109">[out] Массив, используемый для хранения MemberDef токенов.</span><span class="sxs-lookup"><span data-stu-id="d5d68-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d5d68-110">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="d5d68-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d5d68-111">[out] Фактическое число токены MemberDef, возвращаемых в `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="d5d68-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5d68-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5d68-112">Remarks</span></span>  
 <span data-ttu-id="d5d68-113">Этот метод перечисляет поля и методы, но не свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="d5d68-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="d5d68-114">В отличие от [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` отменяет все маркеры полей и элементов, которые имеют указанное имя.</span><span class="sxs-lookup"><span data-stu-id="d5d68-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5d68-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5d68-115">Return Value</span></span>  
  
|<span data-ttu-id="d5d68-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5d68-116">HRESULT</span></span>|<span data-ttu-id="d5d68-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d5d68-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d5d68-118">`EnumTypeDefs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d5d68-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d5d68-119">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d5d68-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="d5d68-120">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="d5d68-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5d68-121">Требования</span><span class="sxs-lookup"><span data-stu-id="d5d68-121">Requirements</span></span>  
 <span data-ttu-id="d5d68-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5d68-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d68-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5d68-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5d68-124">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5d68-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5d68-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d68-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d68-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d5d68-126">See Also</span></span>  
 [<span data-ttu-id="d5d68-127">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d5d68-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d5d68-128">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d5d68-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
