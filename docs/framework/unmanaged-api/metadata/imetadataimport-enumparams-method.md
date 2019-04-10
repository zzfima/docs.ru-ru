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
ms.openlocfilehash: 4ed5ddd74e61e63426871f659aa1c962d38fd534
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221405"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="1cc9a-102">Метод IMetaDataImport::EnumParams</span><span class="sxs-lookup"><span data-stu-id="1cc9a-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="1cc9a-103">Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cc9a-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc9a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cc9a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1cc9a-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1cc9a-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="1cc9a-108">[in] Токен MethodDef, представляющий метод с параметрами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="1cc9a-109">[out] Массив, используемый для хранения токенов ParamDef.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1cc9a-110">[in] Максимальный размер массива `rParams`.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1cc9a-111">[out] Количество возвращаемых в токены ParamDef `rParams`.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cc9a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1cc9a-112">Return Value</span></span>  
  
|<span data-ttu-id="1cc9a-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cc9a-113">HRESULT</span></span>|<span data-ttu-id="1cc9a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1cc9a-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumParams` <span data-ttu-id="1cc9a-115">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1cc9a-116">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="1cc9a-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="1cc9a-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1cc9a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="1cc9a-118">Requirements</span></span>  
 <span data-ttu-id="1cc9a-119">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc9a-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc9a-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1cc9a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1cc9a-121">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cc9a-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1cc9a-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1cc9a-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc9a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1cc9a-123">See also</span></span>

- [<span data-ttu-id="1cc9a-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1cc9a-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1cc9a-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1cc9a-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
