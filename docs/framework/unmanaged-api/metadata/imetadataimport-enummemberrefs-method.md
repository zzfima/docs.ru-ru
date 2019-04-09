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
ms.openlocfilehash: a08577f15a6fab0e630d40032a23c273ee935faa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073001"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="56849-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="56849-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="56849-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="56849-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56849-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56849-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56849-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56849-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="56849-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="56849-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="56849-107">[in] Токен TypeDef, TypeRef, MethodDef или ModuleRef, представляющий тип, члены которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="56849-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="56849-108">[out] Массив, используемый для хранения токены MemberRef.</span><span class="sxs-lookup"><span data-stu-id="56849-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="56849-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="56849-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="56849-110">[out] Фактическое число токены MemberRef, возвращаемых в `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="56849-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56849-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56849-111">Return Value</span></span>  
  
|<span data-ttu-id="56849-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56849-112">HRESULT</span></span>|<span data-ttu-id="56849-113">Описание</span><span class="sxs-lookup"><span data-stu-id="56849-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` <span data-ttu-id="56849-114">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="56849-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="56849-115">Существуют маркеры MemberRef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="56849-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="56849-116">В этом случае `pcTokens` имеет значение нуль.</span><span class="sxs-lookup"><span data-stu-id="56849-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56849-117">Требования</span><span class="sxs-lookup"><span data-stu-id="56849-117">Requirements</span></span>  
 <span data-ttu-id="56849-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56849-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56849-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="56849-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56849-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56849-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="56849-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56849-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56849-122">См. также</span><span class="sxs-lookup"><span data-stu-id="56849-122">See also</span></span>

- [<span data-ttu-id="56849-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="56849-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="56849-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="56849-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
