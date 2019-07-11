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
ms.openlocfilehash: 2f3d74830de0541ec789081c47352beca8d81d74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780712"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="126e0-102">Метод IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="126e0-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="126e0-103">Перечисляет токены определений событий для указанного токена TypeDef.</span><span class="sxs-lookup"><span data-stu-id="126e0-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="126e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="126e0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="126e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="126e0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="126e0-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="126e0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="126e0-107">[in] Токен TypeDef, определения которых событий являются перечисляемые.</span><span class="sxs-lookup"><span data-stu-id="126e0-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="126e0-108">[out] Массив возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="126e0-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="126e0-109">[in] Максимальный размер массива `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="126e0-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="126e0-110">[out] Фактическое число событий, возвращаемых в `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="126e0-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="126e0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="126e0-111">Return Value</span></span>  
  
|<span data-ttu-id="126e0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="126e0-112">HRESULT</span></span>|<span data-ttu-id="126e0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="126e0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="126e0-114">`EnumEvents` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="126e0-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="126e0-115">Нет событий для перечисления.</span><span class="sxs-lookup"><span data-stu-id="126e0-115">There are no events to enumerate.</span></span> <span data-ttu-id="126e0-116">В этом случае `pcEvents` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="126e0-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="126e0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="126e0-117">Requirements</span></span>  
 <span data-ttu-id="126e0-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="126e0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="126e0-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="126e0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="126e0-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="126e0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="126e0-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="126e0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126e0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="126e0-122">See also</span></span>

- [<span data-ttu-id="126e0-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="126e0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="126e0-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="126e0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
