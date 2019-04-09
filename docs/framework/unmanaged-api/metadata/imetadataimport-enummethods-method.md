---
title: Метод IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bab625b8415183b9cf90c35cba140c4d28095805
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076878"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="51f80-102">Метод IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="51f80-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="51f80-103">Перечисляет токены MethodDef, представляющие методы указанного типа.</span><span class="sxs-lookup"><span data-stu-id="51f80-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f80-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51f80-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51f80-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="51f80-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="51f80-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="51f80-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="51f80-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="51f80-108">[in] Токен TypeDef, представляющий тип с методами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="51f80-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="51f80-109">[out] Массив для хранения токенов MethodDef.</span><span class="sxs-lookup"><span data-stu-id="51f80-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="51f80-110">[in] Максимальный размер MethodDef `rMethods` массива.</span><span class="sxs-lookup"><span data-stu-id="51f80-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="51f80-111">[out] Количество токены MethodDef, возвращаемых в `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="51f80-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51f80-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51f80-112">Return Value</span></span>  
  
|<span data-ttu-id="51f80-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51f80-113">HRESULT</span></span>|<span data-ttu-id="51f80-114">Описание</span><span class="sxs-lookup"><span data-stu-id="51f80-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumMethods` <span data-ttu-id="51f80-115">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="51f80-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="51f80-116">Существуют маркеры MethodDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="51f80-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="51f80-117">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="51f80-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51f80-118">Требования</span><span class="sxs-lookup"><span data-stu-id="51f80-118">Requirements</span></span>  
 <span data-ttu-id="51f80-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f80-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f80-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51f80-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51f80-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51f80-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="51f80-122">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="51f80-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51f80-123">См. также</span><span class="sxs-lookup"><span data-stu-id="51f80-123">See also</span></span>

- [<span data-ttu-id="51f80-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="51f80-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="51f80-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="51f80-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
