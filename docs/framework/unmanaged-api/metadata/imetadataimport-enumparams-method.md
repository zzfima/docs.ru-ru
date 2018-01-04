---
title: "Метод IMetaDataImport::EnumParams"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumParams
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51544a44ed4bae25d4214e25c717769a8446f0f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="92297-102">Метод IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="92297-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="92297-103">Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="92297-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92297-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92297-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92297-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="92297-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="92297-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="92297-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="92297-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="92297-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="92297-108">[in] Токен MethodDef, представляющие метод с параметрами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="92297-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="92297-109">[out] Массив, используемый для хранения токены ParamDef.</span><span class="sxs-lookup"><span data-stu-id="92297-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="92297-110">[in] Максимальный размер массива `rParams`.</span><span class="sxs-lookup"><span data-stu-id="92297-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="92297-111">[out] Число токены ParamDef, возвращаемых в `rParams`.</span><span class="sxs-lookup"><span data-stu-id="92297-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92297-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="92297-112">Return Value</span></span>  
  
|<span data-ttu-id="92297-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92297-113">HRESULT</span></span>|<span data-ttu-id="92297-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="92297-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="92297-115">`EnumParams`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="92297-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="92297-116">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="92297-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="92297-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="92297-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92297-118">Требования</span><span class="sxs-lookup"><span data-stu-id="92297-118">Requirements</span></span>  
 <span data-ttu-id="92297-119">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92297-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92297-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92297-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92297-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92297-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92297-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92297-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92297-123">См. также</span><span class="sxs-lookup"><span data-stu-id="92297-123">See Also</span></span>  
 [<span data-ttu-id="92297-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="92297-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="92297-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="92297-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
