---
title: Метод IMetaDataImport::EnumParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b848c30e824d45f6f619cfdb3d00a2d3cdc4573e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="41f3b-102">Метод IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="41f3b-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="41f3b-103">Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="41f3b-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41f3b-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41f3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41f3b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="41f3b-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="41f3b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="41f3b-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="41f3b-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="41f3b-108">[in] Токен MethodDef, представляющие метод с параметрами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="41f3b-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="41f3b-109">[out] Массив, используемый для хранения токены ParamDef.</span><span class="sxs-lookup"><span data-stu-id="41f3b-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="41f3b-110">[in] Максимальный размер массива `rParams`.</span><span class="sxs-lookup"><span data-stu-id="41f3b-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="41f3b-111">[out] Число токены ParamDef, возвращаемых в `rParams`.</span><span class="sxs-lookup"><span data-stu-id="41f3b-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41f3b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="41f3b-112">Return Value</span></span>  
  
|<span data-ttu-id="41f3b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="41f3b-113">HRESULT</span></span>|<span data-ttu-id="41f3b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="41f3b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="41f3b-115">`EnumParams` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="41f3b-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="41f3b-116">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="41f3b-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="41f3b-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="41f3b-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41f3b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="41f3b-118">Requirements</span></span>  
 <span data-ttu-id="41f3b-119">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41f3b-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f3b-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41f3b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41f3b-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41f3b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41f3b-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41f3b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f3b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="41f3b-123">See Also</span></span>  
 [<span data-ttu-id="41f3b-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="41f3b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="41f3b-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="41f3b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
