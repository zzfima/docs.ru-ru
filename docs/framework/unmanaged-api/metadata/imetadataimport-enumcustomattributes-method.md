---
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b53347e9f446d6340bfc5dab2d8f898ebbbf93f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527111"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="c5121-102">Метод IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="c5121-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="c5121-103">Перечисляет токены определений настраиваемых атрибутов, связанных с указанным типом или членом.</span><span class="sxs-lookup"><span data-stu-id="c5121-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5121-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5121-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5121-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c5121-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c5121-106">[in, out] Указатель на возвращенном перечислителе.</span><span class="sxs-lookup"><span data-stu-id="c5121-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="c5121-107">[in] Маркер в рамках перечисление, или ноль для всех настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="c5121-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="c5121-108">[in] Маркер для конструктора типа атрибутов, которые необходимо перечислить или `null` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="c5121-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="c5121-109">[out] Массив настраиваемых атрибутов маркеров.</span><span class="sxs-lookup"><span data-stu-id="c5121-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c5121-110">[in] Максимальный размер массива `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="c5121-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="c5121-111">[out, optional] Фактическое число маркеров значения, возвращаемые в `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="c5121-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5121-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c5121-112">Return Value</span></span>  
  
|<span data-ttu-id="c5121-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5121-113">HRESULT</span></span>|<span data-ttu-id="c5121-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c5121-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c5121-115">`EnumCustomAttributes` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c5121-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c5121-116">Нет никаких настраиваемых атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c5121-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="c5121-117">В этом случае `pcCustomAttributes` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c5121-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5121-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c5121-118">Requirements</span></span>  
 <span data-ttu-id="c5121-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5121-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5121-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5121-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5121-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5121-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5121-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5121-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5121-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c5121-123">See also</span></span>
- [<span data-ttu-id="c5121-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c5121-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c5121-125">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c5121-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
