---
title: "Метод IMetaDataImport::EnumMemberRefs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMemberRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9a47d723aaf7dd83bc488a07b040b43a206be55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="2050e-102">Метод IMetaDataImport::EnumMemberRefs</span><span class="sxs-lookup"><span data-stu-id="2050e-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="2050e-103">Перечисляет токены MemberRef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="2050e-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2050e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2050e-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2050e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2050e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2050e-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="2050e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="2050e-107">[in] Токен TypeDef, TypeRef, MethodDef или ModuleRef, представляющий тип, членами которой являются перечисления.</span><span class="sxs-lookup"><span data-stu-id="2050e-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="2050e-108">[out] Массив, используемый для хранения токены MemberRef.</span><span class="sxs-lookup"><span data-stu-id="2050e-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2050e-109">[in] Максимальный размер массива `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="2050e-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2050e-110">[out] Фактическое число токены MemberRef, возвращаемых в `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="2050e-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2050e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2050e-111">Return Value</span></span>  
  
|<span data-ttu-id="2050e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2050e-112">HRESULT</span></span>|<span data-ttu-id="2050e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2050e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2050e-114">`EnumMemberRefs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2050e-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2050e-115">Существуют маркеры MemberRef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2050e-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="2050e-116">В этом случае `pcTokens` имеет значение нуль.</span><span class="sxs-lookup"><span data-stu-id="2050e-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2050e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2050e-117">Requirements</span></span>  
 <span data-ttu-id="2050e-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2050e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2050e-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2050e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2050e-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2050e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2050e-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2050e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2050e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2050e-122">See Also</span></span>  
 [<span data-ttu-id="2050e-123">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2050e-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="2050e-124">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2050e-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
