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
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440012"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="d3d42-102">Метод IMetaDataImport::EnumEvents</span><span class="sxs-lookup"><span data-stu-id="d3d42-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="d3d42-103">Перечисляет токены определений событий для указанного токена TypeDef.</span><span class="sxs-lookup"><span data-stu-id="d3d42-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3d42-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3d42-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3d42-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3d42-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d3d42-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="d3d42-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="d3d42-107">окне Токен TypeDef, определения событий которого должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="d3d42-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="d3d42-108">заполняет Массив возвращаемых событий.</span><span class="sxs-lookup"><span data-stu-id="d3d42-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d3d42-109">[in] Максимальный размер массива `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="d3d42-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="d3d42-110">заполняет Фактическое число событий, возвращаемых в `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="d3d42-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3d42-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d3d42-111">Return Value</span></span>  
  
|<span data-ttu-id="d3d42-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3d42-112">HRESULT</span></span>|<span data-ttu-id="d3d42-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d3d42-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d3d42-114">`EnumEvents` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="d3d42-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d3d42-115">Нет событий для перечисления.</span><span class="sxs-lookup"><span data-stu-id="d3d42-115">There are no events to enumerate.</span></span> <span data-ttu-id="d3d42-116">В этом случае `pcEvents` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="d3d42-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3d42-117">Требования</span><span class="sxs-lookup"><span data-stu-id="d3d42-117">Requirements</span></span>  
 <span data-ttu-id="d3d42-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3d42-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3d42-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="d3d42-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3d42-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3d42-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3d42-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3d42-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d42-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d3d42-122">See also</span></span>

- [<span data-ttu-id="d3d42-123">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d3d42-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d3d42-124">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d3d42-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
