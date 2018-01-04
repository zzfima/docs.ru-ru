---
title: "Метод IMetaDataImport::EnumMethods"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4052bcd07ec5abd3c560569b59600123350e810c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="d9e7c-102">Метод IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="d9e7c-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="d9e7c-103">Перечисляет токены MethodDef, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9e7c-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9e7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9e7c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d9e7c-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="d9e7c-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="d9e7c-108">[in] Токен TypeDef, представляющий тип с методами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="d9e7c-109">[out] Массив для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d9e7c-110">[in] Максимальный размер MethodDef `rMethods` массива.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d9e7c-111">[out] Число токены MethodDef, возвращаемых в `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e7c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9e7c-112">Return Value</span></span>  
  
|<span data-ttu-id="d9e7c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9e7c-113">HRESULT</span></span>|<span data-ttu-id="d9e7c-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="d9e7c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d9e7c-115">`EnumMethods`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d9e7c-116">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="d9e7c-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="d9e7c-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9e7c-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d9e7c-118">Requirements</span></span>  
 <span data-ttu-id="d9e7c-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e7c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e7c-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9e7c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9e7c-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9e7c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e7c-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e7c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e7c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d9e7c-123">See Also</span></span>  
 [<span data-ttu-id="d9e7c-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d9e7c-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d9e7c-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d9e7c-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
