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
ms.openlocfilehash: b2ba46c025c2d031f0526c6a9da5f6ab07023741
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208453"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="30b9e-102">Метод IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="30b9e-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="30b9e-103">Перечисляет токены определений событий для указанного токена TypeDef.</span><span class="sxs-lookup"><span data-stu-id="30b9e-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30b9e-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30b9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30b9e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="30b9e-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="30b9e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="30b9e-107">[in] Токен TypeDef, определения которых событий являются перечисляемые.</span><span class="sxs-lookup"><span data-stu-id="30b9e-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="30b9e-108">[out] Массив возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="30b9e-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="30b9e-109">[in] Максимальный размер массива `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="30b9e-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="30b9e-110">[out] Фактическое число событий, возвращаемых в `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="30b9e-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30b9e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="30b9e-111">Return Value</span></span>  
  
|<span data-ttu-id="30b9e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30b9e-112">HRESULT</span></span>|<span data-ttu-id="30b9e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="30b9e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="30b9e-114">`EnumEvents` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="30b9e-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="30b9e-115">Нет событий для перечисления.</span><span class="sxs-lookup"><span data-stu-id="30b9e-115">There are no events to enumerate.</span></span> <span data-ttu-id="30b9e-116">В этом случае `pcEvents` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="30b9e-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30b9e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="30b9e-117">Requirements</span></span>  
 <span data-ttu-id="30b9e-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30b9e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30b9e-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="30b9e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30b9e-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30b9e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30b9e-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b9e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b9e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="30b9e-122">See also</span></span>

- [<span data-ttu-id="30b9e-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="30b9e-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="30b9e-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="30b9e-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
