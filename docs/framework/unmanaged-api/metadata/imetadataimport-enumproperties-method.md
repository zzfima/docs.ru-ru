---
title: Метод IMetaDataImport::EnumProperties
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad29204e445bc61b6dc9753d594f0e4bf62930fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448577"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="3d408-102">Метод IMetaDataImport::EnumProperties</span><span class="sxs-lookup"><span data-stu-id="3d408-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="3d408-103">Перечисляет токены PropertyDef, представляющие свойства типа, на который ссылается указанный токен TypeDef.</span><span class="sxs-lookup"><span data-stu-id="3d408-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d408-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d408-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d408-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d408-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3d408-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="3d408-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3d408-107">Это должно быть NULL при первом вызове этого метода.</span><span class="sxs-lookup"><span data-stu-id="3d408-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="3d408-108">[in] Токен TypeDef, представляющий типа со свойствами для перечисления.</span><span class="sxs-lookup"><span data-stu-id="3d408-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="3d408-109">[out] Массив, используемый для хранения токены PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="3d408-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3d408-110">[in] Максимальный размер массива `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="3d408-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="3d408-111">[out] Число токены PropertyDef, возвращаемых в `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="3d408-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d408-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d408-112">Return Value</span></span>  
  
|<span data-ttu-id="3d408-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d408-113">HRESULT</span></span>|<span data-ttu-id="3d408-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3d408-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3d408-115">`EnumProperties` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="3d408-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3d408-116">Существуют маркеры для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="3d408-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="3d408-117">В этом случае `pcProperties` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="3d408-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d408-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3d408-118">Requirements</span></span>  
 <span data-ttu-id="3d408-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d408-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d408-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3d408-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d408-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d408-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d408-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d408-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d408-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3d408-123">See Also</span></span>  
 [<span data-ttu-id="3d408-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3d408-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3d408-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3d408-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
