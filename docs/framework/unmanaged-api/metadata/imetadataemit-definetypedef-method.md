---
title: "Метод IMetaDataEmit::DefineTypeDef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da8fed37605252139428aa40bb3785c242d95cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="bc70a-102">Метод IMetaDataEmit::DefineTypeDef</span><span class="sxs-lookup"><span data-stu-id="bc70a-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="bc70a-103">Создает определение типа для типа среды выполнения и получает маркер метаданных для этого определения типа.</span><span class="sxs-lookup"><span data-stu-id="bc70a-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc70a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc70a-104">Syntax</span></span>  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc70a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc70a-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="bc70a-106">[in] Имя типа в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="bc70a-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="bc70a-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="bc70a-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="bc70a-108">Это битовая маска `CoreTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="bc70a-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="bc70a-109">[in] Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="bc70a-109">[in] The token of the base class.</span></span> <span data-ttu-id="bc70a-110">Он должен быть либо `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="bc70a-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="bc70a-111">[in] Массив маркеров, указав интерфейсов, реализуемых данного класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc70a-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="bc70a-112">[out] `mdTypeDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="bc70a-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc70a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc70a-113">Remarks</span></span>  
 <span data-ttu-id="bc70a-114">Флаг в `dwTypeDefFlags` указывает, является ли тип, который создается общий тип системы ссылочным типом (класс или интерфейс) или общий тип системный тип значения.</span><span class="sxs-lookup"><span data-stu-id="bc70a-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="bc70a-115">В зависимости от параметров, указанные, этот метод в качестве побочного эффекта, могут также создавать `mdInterfaceImpl` записей для каждого интерфейса, реализуемый этим типом или унаследован.</span><span class="sxs-lookup"><span data-stu-id="bc70a-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="bc70a-116">Однако этот метод не возвращает любое из этих `mdInterfaceImpl` маркеры.</span><span class="sxs-lookup"><span data-stu-id="bc70a-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="bc70a-117">Если клиент хочет позднее добавить или изменить `mdInterfaceImpl` токенов, он должен использовать `IMetaDataImport` интерфейса для их перебора.</span><span class="sxs-lookup"><span data-stu-id="bc70a-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="bc70a-118">Если требуется использовать семантику COM `[default]` интерфейса, необходимо предоставить интерфейс по умолчанию как первый элемент в `rtkImplements`; задать класса настраиваемого атрибута покажет, что класс имеет интерфейс по умолчанию (который всегда считается Сначала `mdInterfaceImpl` маркер, объявленным для класса).</span><span class="sxs-lookup"><span data-stu-id="bc70a-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="bc70a-119">Каждый элемент `rtkImplements` массива содержит `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="bc70a-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="bc70a-120">Последним элементом в массиве должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="bc70a-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc70a-121">Требования</span><span class="sxs-lookup"><span data-stu-id="bc70a-121">Requirements</span></span>  
 <span data-ttu-id="bc70a-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc70a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc70a-123">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bc70a-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc70a-124">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc70a-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc70a-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc70a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc70a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="bc70a-126">See Also</span></span>  
 [<span data-ttu-id="bc70a-127">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bc70a-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="bc70a-128">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bc70a-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
