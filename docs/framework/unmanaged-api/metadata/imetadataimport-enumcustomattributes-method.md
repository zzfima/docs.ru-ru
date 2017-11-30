---
title: "Метод IMetaDataImport::EnumCustomAttributes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumCustomAttributes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 78a642ab3c9766ba32537e24814b3b0536df67c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="1d72b-102">Метод IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="1d72b-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="1d72b-103">Перечисляет токены определений настраиваемых атрибутов, связанных с указанным типом или членом.</span><span class="sxs-lookup"><span data-stu-id="1d72b-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d72b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d72b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1d72b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d72b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1d72b-106">[in, out] Указатель на возвращаемый перечислитель.</span><span class="sxs-lookup"><span data-stu-id="1d72b-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="1d72b-107">[in] Токен для области перечисления или нулевое значение для всех настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="1d72b-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="1d72b-108">[in] Токен для конструктора типа атрибутов, которые необходимо перечислить или `null` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="1d72b-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="1d72b-109">[out] Массив настраиваемых атрибутов маркеров.</span><span class="sxs-lookup"><span data-stu-id="1d72b-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1d72b-110">[in] Максимальный размер массива `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="1d72b-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="1d72b-111">[out, optional] Фактическое число маркеров значения, возвращаемые в `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="1d72b-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d72b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d72b-112">Return Value</span></span>  
  
|<span data-ttu-id="1d72b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d72b-113">HRESULT</span></span>|<span data-ttu-id="1d72b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1d72b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1d72b-115">`EnumCustomAttributes`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1d72b-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1d72b-116">Нет никаких пользовательских атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="1d72b-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="1d72b-117">В этом случае `pcCustomAttributes` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="1d72b-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d72b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="1d72b-118">Requirements</span></span>  
 <span data-ttu-id="1d72b-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d72b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d72b-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d72b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d72b-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d72b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d72b-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d72b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d72b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1d72b-123">See Also</span></span>  
 [<span data-ttu-id="1d72b-124">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1d72b-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1d72b-125">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1d72b-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
