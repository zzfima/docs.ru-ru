---
title: Метод IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175763"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="3b449-102">Метод IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="3b449-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="3b449-103">Создает определение типа для общего типа времени выполнения языка и получает токен метаданных для определения этого типа.</span><span class="sxs-lookup"><span data-stu-id="3b449-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b449-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b449-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b449-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b449-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="3b449-106">(в) Название типа в Unicode.</span><span class="sxs-lookup"><span data-stu-id="3b449-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="3b449-107">(в) `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="3b449-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="3b449-108">Это битмаска ценностей. `CoreTypeAttr`</span><span class="sxs-lookup"><span data-stu-id="3b449-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="3b449-109">(в) Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="3b449-109">[in] The token of the base class.</span></span> <span data-ttu-id="3b449-110">Это должен быть `mdTypeDef` либо `mdTypeRef` знак, либо жетон.</span><span class="sxs-lookup"><span data-stu-id="3b449-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="3b449-111">(в) Массив токенов, указывающих интерфейсы, которые реализует этот класс или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3b449-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="3b449-112">(ваут) Назначенный `mdTypeDef` маркер.</span><span class="sxs-lookup"><span data-stu-id="3b449-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b449-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3b449-113">Remarks</span></span>  
 <span data-ttu-id="3b449-114">Флаг в `dwTypeDefFlags` опознавательных данных определяет, является ли создаваемый тип обычным типом системы (класс или интерфейс) или общим типом значения системы.</span><span class="sxs-lookup"><span data-stu-id="3b449-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="3b449-115">В зависимости от поставленных параметров, этот метод, как `mdInterfaceImpl` побочный эффект, может также создать запись для каждого интерфейса, который наследуется или реализован этим типом.</span><span class="sxs-lookup"><span data-stu-id="3b449-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="3b449-116">Однако этот метод не возвращает `mdInterfaceImpl` ни одного из этих токенов.</span><span class="sxs-lookup"><span data-stu-id="3b449-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="3b449-117">Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркер, он должен использовать `IMetaDataImport` интерфейс для их перечисления.</span><span class="sxs-lookup"><span data-stu-id="3b449-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="3b449-118">Если вы хотите использовать семантику интерфейса `[default]` COM, следует предоставить `rtkImplements`интерфейс по умолчанию в качестве первого элемента в; пользовательский набор атрибутов в классе будет указывать на то, что класс `mdInterfaceImpl` имеет интерфейс по умолчанию (который всегда считается первым маркером, объявленным для класса).</span><span class="sxs-lookup"><span data-stu-id="3b449-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="3b449-119">Каждый элемент `rtkImplements` массива `mdTypeDef` `mdTypeRef` содержит маркер или жетон.</span><span class="sxs-lookup"><span data-stu-id="3b449-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="3b449-120">Последний элемент в массиве должен быть. `mdTokenNil`</span><span class="sxs-lookup"><span data-stu-id="3b449-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b449-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3b449-121">Requirements</span></span>  
 <span data-ttu-id="3b449-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b449-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b449-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b449-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b449-124">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b449-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b449-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b449-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b449-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b449-126">See also</span></span>

- [<span data-ttu-id="3b449-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3b449-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b449-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3b449-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
