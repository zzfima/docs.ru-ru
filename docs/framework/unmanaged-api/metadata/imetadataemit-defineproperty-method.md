---
title: Метод IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431521"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="ef551-102">Метод IMetaDataEmit::DefineProperty</span><span class="sxs-lookup"><span data-stu-id="ef551-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="ef551-103">Создает определение свойства для указанного типа с указанными методами доступа `get` и `set` и получает маркер для этого определения свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef551-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef551-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef551-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef551-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ef551-106">окне Токен для класса или интерфейса, для которого определяется свойство.</span><span class="sxs-lookup"><span data-stu-id="ef551-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="ef551-107">окне Имя свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="ef551-108">окне Флаги свойств.</span><span class="sxs-lookup"><span data-stu-id="ef551-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="ef551-109">окне Сигнатура свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="ef551-110">окне Число байтов в `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="ef551-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ef551-111">окне Тип значения свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef551-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ef551-112">окне Значение по умолчанию для свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ef551-113">окне Число символов Юникода в `pValue`.</span><span class="sxs-lookup"><span data-stu-id="ef551-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="ef551-114">окне Метод, который задает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="ef551-115">окне Метод, который получает значение свойства.</span><span class="sxs-lookup"><span data-stu-id="ef551-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="ef551-116">окне Массив других методов, связанных со свойством.</span><span class="sxs-lookup"><span data-stu-id="ef551-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="ef551-117">Завершите работу массива с помощью `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="ef551-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="ef551-118">заполняет Назначенный маркер `mdProperty`.</span><span class="sxs-lookup"><span data-stu-id="ef551-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef551-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ef551-119">Requirements</span></span>  
 <span data-ttu-id="ef551-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef551-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef551-121">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ef551-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef551-122">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef551-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef551-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef551-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef551-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ef551-124">See also</span></span>

- [<span data-ttu-id="ef551-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ef551-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ef551-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ef551-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
