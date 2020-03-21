---
title: Метод IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177553"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="29940-102">Метод IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="29940-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="29940-103">Устанавливает или обновляет значение по умолчанию для поля, на который ссылается указанный маркер поля.</span><span class="sxs-lookup"><span data-stu-id="29940-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29940-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29940-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29940-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29940-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="29940-106">(в) Токен для целевого поля.</span><span class="sxs-lookup"><span data-stu-id="29940-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="29940-107">(в) Полевые атрибуты.</span><span class="sxs-lookup"><span data-stu-id="29940-107">[in] Field attributes.</span></span> <span data-ttu-id="29940-108">Это битмаска ценностей. `CorFieldAttr`</span><span class="sxs-lookup"><span data-stu-id="29940-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="29940-109">(в) Для `ELEMENT_TYPE_` *\** постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="29940-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="29940-110">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="29940-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="29940-111">Если константа не определена, `ELEMENT_TYPE_END`установите это значение.</span><span class="sxs-lookup"><span data-stu-id="29940-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="29940-112">(в) Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="29940-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="29940-113">(в) Размер, в unicode символов, из `pValue`.</span><span class="sxs-lookup"><span data-stu-id="29940-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29940-114">Требования</span><span class="sxs-lookup"><span data-stu-id="29940-114">Requirements</span></span>  
 <span data-ttu-id="29940-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29940-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29940-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="29940-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="29940-117">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29940-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29940-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29940-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29940-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29940-119">See also</span></span>

- [<span data-ttu-id="29940-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="29940-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="29940-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="29940-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
