---
title: Метод IMetaDataImport::EnumMethodImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75d1ce526d4cba025ea6e9db8281023969e7cb0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="9cf84-102">Метод IMetaDataImport::EnumMethodImpls</span><span class="sxs-lookup"><span data-stu-id="9cf84-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="9cf84-103">Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="9cf84-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cf84-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cf84-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cf84-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9cf84-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="9cf84-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9cf84-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="9cf84-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="9cf84-108">[in] TypeDef для типа токена которого реализации метода для перечисления.</span><span class="sxs-lookup"><span data-stu-id="9cf84-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="9cf84-109">[out] Массив для хранения токены MethodBody.</span><span class="sxs-lookup"><span data-stu-id="9cf84-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="9cf84-110">[out] Массив для хранения токенов Объявление_метода.</span><span class="sxs-lookup"><span data-stu-id="9cf84-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9cf84-111">[in] Максимальный размер `rMethodBody` и `rMethodDecl` массивов.</span><span class="sxs-lookup"><span data-stu-id="9cf84-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="9cf84-112">[in] Фактическое число методов, возвращаемый в `rMethodBody` и `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="9cf84-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cf84-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cf84-113">Return Value</span></span>  
  
|<span data-ttu-id="9cf84-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cf84-114">HRESULT</span></span>|<span data-ttu-id="9cf84-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9cf84-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9cf84-116">`EnumMethodImpls` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9cf84-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9cf84-117">Существуют маркеры нет метода для перечисления.</span><span class="sxs-lookup"><span data-stu-id="9cf84-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="9cf84-118">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="9cf84-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9cf84-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9cf84-119">Requirements</span></span>  
 <span data-ttu-id="9cf84-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cf84-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cf84-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9cf84-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cf84-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9cf84-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cf84-123">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cf84-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf84-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9cf84-124">See Also</span></span>  
 [<span data-ttu-id="9cf84-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9cf84-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9cf84-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9cf84-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
