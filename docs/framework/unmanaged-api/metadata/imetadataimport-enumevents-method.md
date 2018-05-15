---
title: Метод IMetaDataImport::EnumEvents
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 608b4a7d147124ede60e9d81f91600dfdaad0a65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="f1ed4-102">Метод IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="f1ed4-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="f1ed4-103">Перечисляет токены определений событий для указанного токена TypeDef.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1ed4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1ed4-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1ed4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1ed4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f1ed4-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="f1ed4-107">[in] Маркер TypeDef, определения событий, для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="f1ed4-108">[out] Массив возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f1ed4-109">[in] Максимальный размер массива `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="f1ed4-110">[out] Фактическое число событий, возвращенное в `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1ed4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f1ed4-111">Return Value</span></span>  
  
|<span data-ttu-id="f1ed4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1ed4-112">HRESULT</span></span>|<span data-ttu-id="f1ed4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f1ed4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f1ed4-114">`EnumEvents` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f1ed4-115">Нет событий для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-115">There are no events to enumerate.</span></span> <span data-ttu-id="f1ed4-116">В этом случае `pcEvents` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="f1ed4-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1ed4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f1ed4-117">Requirements</span></span>  
 <span data-ttu-id="f1ed4-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ed4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ed4-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1ed4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1ed4-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1ed4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1ed4-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ed4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ed4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1ed4-122">See Also</span></span>  
 [<span data-ttu-id="f1ed4-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f1ed4-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f1ed4-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f1ed4-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
