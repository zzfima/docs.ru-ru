---
title: "Метод IMetaDataAssemblyImport::EnumAssemblyRefs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumAssemblyRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18dda94ac9a19a7cabbaa2a9c4cc83badb079f92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="2fc1f-102">Метод IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="2fc1f-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="2fc1f-103">Перечисляет `mdAssemblyRef` экземпляров, определенных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc1f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fc1f-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fc1f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fc1f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2fc1f-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2fc1f-107">Это должен быть значением null значения при `EnumAssemblyRefs` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="2fc1f-108">[out] Перечисление `mdAssemblyRef` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2fc1f-109">[in] Максимальное количество маркеров, которые могут быть помещены в `rAssemblyRefs` массива.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2fc1f-110">[out] Число маркеров непосредственно в `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fc1f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2fc1f-111">Return Value</span></span>  
  
|<span data-ttu-id="2fc1f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fc1f-112">HRESULT</span></span>|<span data-ttu-id="2fc1f-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="2fc1f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2fc1f-114">`EnumAssemblyRefs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2fc1f-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2fc1f-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2fc1f-117">Требования</span><span class="sxs-lookup"><span data-stu-id="2fc1f-117">Requirements</span></span>  
 <span data-ttu-id="2fc1f-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fc1f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc1f-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2fc1f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fc1f-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fc1f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fc1f-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc1f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc1f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2fc1f-122">See Also</span></span>  
 [<span data-ttu-id="2fc1f-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="2fc1f-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
