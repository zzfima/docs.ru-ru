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
ms.openlocfilehash: ab5200cbd3a37bba31d52f9934e11aecc88c59c0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502414"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="7ce82-102">Метод IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="7ce82-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="7ce82-103">Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="7ce82-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ce82-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce82-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ce82-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7ce82-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="7ce82-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7ce82-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="7ce82-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="7ce82-108">[in] Токен MethodDef, представляющий метод с параметрами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="7ce82-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="7ce82-109">[out] Массив, используемый для хранения токенов ParamDef.</span><span class="sxs-lookup"><span data-stu-id="7ce82-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7ce82-110">[in] Максимальный размер массива `rParams`.</span><span class="sxs-lookup"><span data-stu-id="7ce82-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7ce82-111">[out] Количество возвращаемых в токены ParamDef `rParams`.</span><span class="sxs-lookup"><span data-stu-id="7ce82-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ce82-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7ce82-112">Return Value</span></span>  
  
|<span data-ttu-id="7ce82-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ce82-113">HRESULT</span></span>|<span data-ttu-id="7ce82-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="7ce82-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7ce82-115">`EnumParams` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="7ce82-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7ce82-116">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="7ce82-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="7ce82-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="7ce82-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ce82-118">Требования</span><span class="sxs-lookup"><span data-stu-id="7ce82-118">Requirements</span></span>  
 <span data-ttu-id="7ce82-119">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce82-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce82-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ce82-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ce82-121">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ce82-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ce82-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce82-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce82-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7ce82-123">See also</span></span>
- [<span data-ttu-id="7ce82-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7ce82-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7ce82-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7ce82-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
