---
title: "Метод IMetaDataImport::EnumTypeRefs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumTypeRefs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3099f129abd3477aeb08526b9f0dcd5b701d4dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="a13b1-102">Метод IMetaDataImport::EnumTypeRefs</span><span class="sxs-lookup"><span data-stu-id="a13b1-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="a13b1-103">Перечисляет токены TypeRef, определенные в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="a13b1-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a13b1-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a13b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a13b1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a13b1-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a13b1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a13b1-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="a13b1-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="a13b1-108">[out] Массив, используемый для хранения токены TypeRef.</span><span class="sxs-lookup"><span data-stu-id="a13b1-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a13b1-109">[in] Максимальный размер массива `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="a13b1-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="a13b1-110">[out] Указатель на число токены TypeRef, возвращаемых в `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="a13b1-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a13b1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a13b1-111">Return Value</span></span>  
  
|<span data-ttu-id="a13b1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a13b1-112">HRESULT</span></span>|<span data-ttu-id="a13b1-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="a13b1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a13b1-114">`EnumTypeRefs`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a13b1-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a13b1-115">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="a13b1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a13b1-116">В этом случае `pcTypeRefs` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="a13b1-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a13b1-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="a13b1-117">Remarks</span></span>  
 <span data-ttu-id="a13b1-118">Лексема TypeRef представляет ссылку на тип.</span><span class="sxs-lookup"><span data-stu-id="a13b1-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13b1-119">Требования</span><span class="sxs-lookup"><span data-stu-id="a13b1-119">Requirements</span></span>  
 <span data-ttu-id="a13b1-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13b1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13b1-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a13b1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a13b1-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a13b1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a13b1-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13b1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13b1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a13b1-124">See Also</span></span>  
 [<span data-ttu-id="a13b1-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a13b1-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a13b1-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a13b1-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
