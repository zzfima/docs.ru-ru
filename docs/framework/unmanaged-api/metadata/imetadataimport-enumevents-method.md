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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042743"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="f2fde-102">Метод IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="f2fde-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="f2fde-103">Перечисляет токены определений событий для указанного токена TypeDef.</span><span class="sxs-lookup"><span data-stu-id="f2fde-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2fde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2fde-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2fde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2fde-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f2fde-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="f2fde-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="f2fde-107">[in] Токен TypeDef, определения которых событий являются перечисляемые.</span><span class="sxs-lookup"><span data-stu-id="f2fde-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="f2fde-108">[out] Массив возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="f2fde-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f2fde-109">[in] Максимальный размер массива `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f2fde-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="f2fde-110">[out] Фактическое число событий, возвращаемых в `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="f2fde-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2fde-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2fde-111">Return Value</span></span>  
  
|<span data-ttu-id="f2fde-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2fde-112">HRESULT</span></span>|<span data-ttu-id="f2fde-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f2fde-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f2fde-114">`EnumEvents` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f2fde-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f2fde-115">Нет событий для перечисления.</span><span class="sxs-lookup"><span data-stu-id="f2fde-115">There are no events to enumerate.</span></span> <span data-ttu-id="f2fde-116">В этом случае `pcEvents` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="f2fde-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2fde-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f2fde-117">Requirements</span></span>  
 <span data-ttu-id="f2fde-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2fde-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2fde-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2fde-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2fde-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2fde-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2fde-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2fde-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fde-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f2fde-122">See also</span></span>

- [<span data-ttu-id="f2fde-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f2fde-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f2fde-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f2fde-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
