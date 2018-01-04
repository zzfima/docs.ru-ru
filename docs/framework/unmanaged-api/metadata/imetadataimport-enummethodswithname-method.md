---
title: "Метод IMetaDataImport::EnumMethodsWithName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodsWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f16e66f83925104c4be1e69a476e398f33295a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="8a0fb-102">Метод IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="8a0fb-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="8a0fb-103">Перечисляет методы с заданным именем, определяемые по типу, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a0fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a0fb-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a0fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a0fb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8a0fb-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8a0fb-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="8a0fb-108">[in] Токен TypeDef, представляющий тип, методы которого для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="8a0fb-109">[in] Имя, которое ограничивает область перечисления.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="8a0fb-110">[out] Массив, используемый для хранения токены MethodDef.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8a0fb-111">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8a0fb-112">[out] Число токены MethodDef, возвращаемых в `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a0fb-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8a0fb-113">Remarks</span></span>  
 <span data-ttu-id="8a0fb-114">Этот метод перечисляет поля и методы, но не свойств или событий.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="8a0fb-115">В отличие от [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` отменяет все метод маркеры, которые имеют указанное имя.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a0fb-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8a0fb-116">Return Value</span></span>  
  
|<span data-ttu-id="8a0fb-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a0fb-117">HRESULT</span></span>|<span data-ttu-id="8a0fb-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="8a0fb-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8a0fb-119">`EnumMethodsWithName`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8a0fb-120">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="8a0fb-121">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="8a0fb-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a0fb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8a0fb-122">Requirements</span></span>  
 <span data-ttu-id="8a0fb-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a0fb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a0fb-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a0fb-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a0fb-125">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a0fb-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a0fb-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a0fb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0fb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8a0fb-127">See Also</span></span>  
 [<span data-ttu-id="8a0fb-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8a0fb-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8a0fb-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8a0fb-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
