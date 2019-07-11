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
ms.openlocfilehash: 9e78c4d7319a931ca7090d6f99651bc9660e4af8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782042"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="7763d-102">Метод IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="7763d-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="7763d-103">Задает хранится в метаданных для свойства, определенные с помощью предыдущего вызова функции [метод DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7763d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7763d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="7763d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7763d-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="7763d-106">[in] Токен для свойства, которые необходимо изменить</span><span class="sxs-lookup"><span data-stu-id="7763d-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="7763d-107">[in] Флаги свойства.</span><span class="sxs-lookup"><span data-stu-id="7763d-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7763d-108">[in] Тип значения свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7763d-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7763d-109">[in] Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="7763d-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7763d-110">[in] Количество (Юникод) символы в `pValue`.</span><span class="sxs-lookup"><span data-stu-id="7763d-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="7763d-111">[in] Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="7763d-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="7763d-112">[in] Метод, который возвращает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="7763d-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="7763d-113">[in] Массив, другие методы, связанные со свойством.</span><span class="sxs-lookup"><span data-stu-id="7763d-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="7763d-114">Этот массив `mdTokenNil` токена.</span><span class="sxs-lookup"><span data-stu-id="7763d-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7763d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7763d-115">Requirements</span></span>  
 <span data-ttu-id="7763d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7763d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7763d-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7763d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7763d-118">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7763d-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7763d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7763d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7763d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7763d-120">See also</span></span>

- [<span data-ttu-id="7763d-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7763d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7763d-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7763d-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
