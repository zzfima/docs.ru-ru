---
title: Метод IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a56d874e5e7ef491c24b0aef2ace700087de677
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447415"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="3c101-102">Метод IMetaDataAssemblyImport::EnumAssemblyRefs</span><span class="sxs-lookup"><span data-stu-id="3c101-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="3c101-103">Перечисляет `mdAssemblyRef` экземпляров, определенных в манифесте сборки.</span><span class="sxs-lookup"><span data-stu-id="3c101-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c101-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c101-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c101-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c101-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3c101-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="3c101-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3c101-107">Это должен быть значением null значения при `EnumAssemblyRefs` метод вызывается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="3c101-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="3c101-108">[out] Перечисление `mdAssemblyRef` токены метаданных.</span><span class="sxs-lookup"><span data-stu-id="3c101-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c101-109">[in] Максимальное количество маркеров, которые могут быть помещены в `rAssemblyRefs` массива.</span><span class="sxs-lookup"><span data-stu-id="3c101-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3c101-110">[out] Число маркеров непосредственно в `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="3c101-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c101-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c101-111">Return Value</span></span>  
  
|<span data-ttu-id="3c101-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c101-112">HRESULT</span></span>|<span data-ttu-id="3c101-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3c101-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c101-114">`EnumAssemblyRefs` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3c101-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c101-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="3c101-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3c101-116">В этом случае `pcTokens` присваивается нулевое значение.</span><span class="sxs-lookup"><span data-stu-id="3c101-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c101-117">Требования</span><span class="sxs-lookup"><span data-stu-id="3c101-117">Requirements</span></span>  
 <span data-ttu-id="3c101-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c101-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c101-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c101-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c101-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c101-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c101-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c101-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c101-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3c101-122">See Also</span></span>  
 [<span data-ttu-id="3c101-123">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3c101-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
