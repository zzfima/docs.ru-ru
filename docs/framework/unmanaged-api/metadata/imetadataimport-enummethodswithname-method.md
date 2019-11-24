---
title: Метод IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450057"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="b5b38-102">Метод IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="b5b38-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="b5b38-103">Перечисляет методы с заданным именем, определяемые по типу, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="b5b38-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5b38-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5b38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5b38-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b5b38-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="b5b38-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b5b38-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="b5b38-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="b5b38-108">[in] A TypeDef token representing the type whose methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="b5b38-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5b38-109">[in] The name that limits the scope of the enumeration.</span><span class="sxs-lookup"><span data-stu-id="b5b38-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="b5b38-110">[out] The array used to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="b5b38-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b5b38-111">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="b5b38-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b5b38-112">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="b5b38-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5b38-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="b5b38-113">Remarks</span></span>  
 <span data-ttu-id="b5b38-114">This method enumerates fields and methods, but not properties or events.</span><span class="sxs-lookup"><span data-stu-id="b5b38-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="b5b38-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span><span class="sxs-lookup"><span data-stu-id="b5b38-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5b38-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5b38-116">Return Value</span></span>  
  
|<span data-ttu-id="b5b38-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5b38-117">HRESULT</span></span>|<span data-ttu-id="b5b38-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b5b38-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b5b38-119">`EnumMethodsWithName` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="b5b38-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b5b38-120">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="b5b38-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="b5b38-121">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="b5b38-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5b38-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b5b38-122">Requirements</span></span>  
 <span data-ttu-id="b5b38-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5b38-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b38-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5b38-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5b38-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5b38-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5b38-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5b38-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b38-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b5b38-127">See also</span></span>

- [<span data-ttu-id="b5b38-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b5b38-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b5b38-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b5b38-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
