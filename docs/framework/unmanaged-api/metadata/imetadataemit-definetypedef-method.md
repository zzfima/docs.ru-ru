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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a1da4015a202debe1d864f3c0135cc296ce6fce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605480"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="655ab-102">Метод IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="655ab-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="655ab-103">Создает определение типа для типа среды выполнения и получает маркер метаданных для этого определения типа.</span><span class="sxs-lookup"><span data-stu-id="655ab-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="655ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="655ab-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="655ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="655ab-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="655ab-106">[in] Имя типа в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="655ab-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="655ab-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="655ab-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="655ab-108">Это битовая маска `CoreTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="655ab-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="655ab-109">[in] Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="655ab-109">[in] The token of the base class.</span></span> <span data-ttu-id="655ab-110">Он должен быть либо `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="655ab-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="655ab-111">[in] Массив токенов, указав интерфейсы, реализуемые этот класс или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="655ab-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="655ab-112">[out] `mdTypeDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="655ab-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="655ab-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="655ab-113">Remarks</span></span>  
 <span data-ttu-id="655ab-114">Флаг в `dwTypeDefFlags` указывает, является ли тип, который создается общий тип системы ссылочным типом (класс или интерфейс) или общие системные типы значений типа.</span><span class="sxs-lookup"><span data-stu-id="655ab-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="655ab-115">В зависимости от параметров, содержащихся, этот метод в качестве побочного эффекта, может также создавать `mdInterfaceImpl` записей для каждого интерфейса, реализуемый этим типом или унаследован.</span><span class="sxs-lookup"><span data-stu-id="655ab-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="655ab-116">Тем не менее, этот метод не возвращает любое из этих `mdInterfaceImpl` маркеры.</span><span class="sxs-lookup"><span data-stu-id="655ab-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="655ab-117">Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркеров, он должен использовать `IMetaDataImport` интерфейс для их перебора.</span><span class="sxs-lookup"><span data-stu-id="655ab-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="655ab-118">Если вы хотите использовать семантику COM `[default]` интерфейс, должны предоставлять интерфейс по умолчанию, как первый элемент в `rtkImplements`; задать класса настраиваемого атрибута укажет, что класс имеет интерфейс по умолчанию (который всегда предполагается, что Сначала `mdInterfaceImpl` маркер, объявленным для класса).</span><span class="sxs-lookup"><span data-stu-id="655ab-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="655ab-119">Каждый элемент `rtkImplements` массива содержит `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="655ab-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="655ab-120">Последним элементом в массиве должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="655ab-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="655ab-121">Требования</span><span class="sxs-lookup"><span data-stu-id="655ab-121">Requirements</span></span>  
 <span data-ttu-id="655ab-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="655ab-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="655ab-123">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="655ab-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="655ab-124">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="655ab-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="655ab-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="655ab-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655ab-126">См. также</span><span class="sxs-lookup"><span data-stu-id="655ab-126">See also</span></span>
- [<span data-ttu-id="655ab-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="655ab-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="655ab-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="655ab-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
