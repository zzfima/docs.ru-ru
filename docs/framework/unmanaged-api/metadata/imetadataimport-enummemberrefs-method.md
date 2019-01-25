---
title: Метод IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34a6762618780b22bcd8be376209912390524578
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592024"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="d5d38-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="d5d38-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="d5d38-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="d5d38-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5d38-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5d38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d5d38-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d5d38-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="d5d38-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="d5d38-107">[in] Токен TypeDef, TypeRef, MethodDef или ModuleRef, представляющий тип, члены которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="d5d38-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="d5d38-108">[out] Массив, используемый для хранения токены MemberRef.</span><span class="sxs-lookup"><span data-stu-id="d5d38-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d5d38-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="d5d38-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d5d38-110">[out] Фактическое число токены MemberRef, возвращаемых в `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="d5d38-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5d38-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d5d38-111">Return Value</span></span>  
  
|<span data-ttu-id="d5d38-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5d38-112">HRESULT</span></span>|<span data-ttu-id="d5d38-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="d5d38-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d5d38-114">`EnumMemberRefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d5d38-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d5d38-115">Существуют маркеры MemberRef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d5d38-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="d5d38-116">В этом случае `pcTokens` имеет значение нуль.</span><span class="sxs-lookup"><span data-stu-id="d5d38-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5d38-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d5d38-117">Requirements</span></span>  
 <span data-ttu-id="d5d38-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5d38-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d38-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5d38-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5d38-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5d38-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5d38-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d38-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d38-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d5d38-122">See also</span></span>
- [<span data-ttu-id="d5d38-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d5d38-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d5d38-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d5d38-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
