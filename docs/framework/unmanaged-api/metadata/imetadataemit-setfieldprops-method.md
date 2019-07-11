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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ccafea78aa2497c52442a10ad1af1c05771df7e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737106"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="ee63a-102">Метод IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="ee63a-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="ee63a-103">Задает или обновляет значение по умолчанию для поля, который ссылается токен указанного поля.</span><span class="sxs-lookup"><span data-stu-id="ee63a-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee63a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee63a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee63a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee63a-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="ee63a-106">[in] Маркер целевого поля.</span><span class="sxs-lookup"><span data-stu-id="ee63a-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="ee63a-107">[in] Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="ee63a-107">[in] Field attributes.</span></span> <span data-ttu-id="ee63a-108">Это битовая маска `CorFieldAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="ee63a-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ee63a-109">[in] `ELEMENT_TYPE_` *\** Для постоянного значения.</span><span class="sxs-lookup"><span data-stu-id="ee63a-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="ee63a-110">Это `CorElementType` значение.</span><span class="sxs-lookup"><span data-stu-id="ee63a-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="ee63a-111">Если не определяется константой, это значение равно `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="ee63a-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ee63a-112">[in] Постоянное значение для поля.</span><span class="sxs-lookup"><span data-stu-id="ee63a-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ee63a-113">[in] Размер в символы Юникода из `pValue`.</span><span class="sxs-lookup"><span data-stu-id="ee63a-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee63a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ee63a-114">Requirements</span></span>  
 <span data-ttu-id="ee63a-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee63a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee63a-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ee63a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee63a-117">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee63a-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee63a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee63a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee63a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ee63a-119">See also</span></span>

- [<span data-ttu-id="ee63a-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ee63a-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ee63a-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ee63a-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
