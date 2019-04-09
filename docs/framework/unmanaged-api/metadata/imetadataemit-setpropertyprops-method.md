---
title: Метод IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdee8491b22675fb8dd8fa89e77ebf8541185173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207900"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="6e4e6-102">Метод IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="6e4e6-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="6e4e6-103">Задает хранится в метаданных для свойства, определенные с помощью предыдущего вызова функции [метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="6e4e6-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e4e6-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6e4e6-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="6e4e6-106">[in] Токен для свойства, которые необходимо изменить</span><span class="sxs-lookup"><span data-stu-id="6e4e6-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="6e4e6-107">[in] Флаги свойства.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="6e4e6-108">[in] Тип значения свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6e4e6-109">[in] Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="6e4e6-110">[in] Количество (Юникод) символы в `pValue`.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="6e4e6-111">[in] Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="6e4e6-112">[in] Метод, который возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6e4e6-113">[in] Массив, другие методы, связанные со свойством.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="6e4e6-114">Этот массив `mdTokenNil` токена.</span><span class="sxs-lookup"><span data-stu-id="6e4e6-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4e6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6e4e6-115">Requirements</span></span>  
 <span data-ttu-id="6e4e6-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e4e6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e4e6-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e4e6-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e4e6-118">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e4e6-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6e4e6-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6e4e6-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e4e6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6e4e6-120">See also</span></span>

- [<span data-ttu-id="6e4e6-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6e4e6-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6e4e6-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6e4e6-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
