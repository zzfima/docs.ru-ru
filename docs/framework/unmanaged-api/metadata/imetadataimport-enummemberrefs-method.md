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
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177334"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="d6494-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="d6494-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="d6494-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="d6494-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6494-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6494-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6494-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6494-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d6494-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="d6494-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="d6494-107">(в) Токен TypeDef, TypeRef, MethodDef или ModuleRef для типа, члены которого должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="d6494-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="d6494-108">(ваут) Массив, используемый для хранения токенов MemberRef.</span><span class="sxs-lookup"><span data-stu-id="d6494-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d6494-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="d6494-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d6494-110">(ваут) Фактическое количество возвращенных токенов `rMemberRefs`MemberRef в .</span><span class="sxs-lookup"><span data-stu-id="d6494-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6494-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d6494-111">Return Value</span></span>  
  
|<span data-ttu-id="d6494-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6494-112">HRESULT</span></span>|<span data-ttu-id="d6494-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d6494-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d6494-114">`EnumMemberRefs`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="d6494-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d6494-115">Нет токенов MemberRef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="d6494-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="d6494-116">В этом `pcTokens` случае, до нуля.</span><span class="sxs-lookup"><span data-stu-id="d6494-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6494-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d6494-117">Requirements</span></span>  
 <span data-ttu-id="d6494-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6494-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6494-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d6494-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6494-120">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6494-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6494-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6494-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6494-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d6494-122">See also</span></span>

- [<span data-ttu-id="d6494-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d6494-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d6494-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d6494-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
