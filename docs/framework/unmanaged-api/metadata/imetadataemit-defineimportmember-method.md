---
title: Метод IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175867"
---
# <a name="imetadataemitdefineimportmember-method"></a><span data-ttu-id="13104-102">Метод IMetaDataEmit::DefineImportMember</span><span class="sxs-lookup"><span data-stu-id="13104-102">IMetaDataEmit::DefineImportMember Method</span></span>
<span data-ttu-id="13104-103">Создает ссылку на указанный член типа или модуля, который определяется вне текущей области, и определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="13104-103">Creates a reference to the specified member of a type or module that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13104-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13104-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13104-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13104-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="13104-106">(в) [Интерфейс IMetaDataAssemblyImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) представляющий сборку, из которой импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="13104-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target member is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="13104-107">(в) Массив, содержащий хэш для сборки, `pAssemImport`указанный .</span><span class="sxs-lookup"><span data-stu-id="13104-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="13104-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="13104-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="13104-109">(в) Интерфейс [IMetaDataImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) представляющий область метаданных, из которой импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="13104-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target member is imported.</span></span>  
  
 `mbMember`  
 <span data-ttu-id="13104-110">(в) Токен метаданных, опозначавший целевой символ.</span><span class="sxs-lookup"><span data-stu-id="13104-110">[in] The metadata token that specifies the target member.</span></span> <span data-ttu-id="13104-111">Токен может быть `mdMethodDef` (для элемента) `mdProperty` (для свойства `mdFieldDef` участника) или (для поля участника) маркера.</span><span class="sxs-lookup"><span data-stu-id="13104-111">The token can be an `mdMethodDef` (for a member method), `mdProperty` (for a member property), or `mdFieldDef` (for a member field) token.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="13104-112">(в) Интерфейс [IMetaDataAssemblyEmit,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) представляющий сборку, в которую импортируется целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="13104-112">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target member is imported.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="13104-113">(в) `mdTypeRef` Токен `mdModuleRef` или токен для типа или модуля, соответственно, который владеет целевым членом.</span><span class="sxs-lookup"><span data-stu-id="13104-113">[in] The `mdTypeRef` or `mdModuleRef` token for the type or module, respectively, that owns the target member.</span></span>  
  
 `pmr`  
 <span data-ttu-id="13104-114">(ваут) Токен, `mdMemberRef` определяемый в текущей области для ссылки участника.</span><span class="sxs-lookup"><span data-stu-id="13104-114">[out] The `mdMemberRef` token that is defined in the current scope for the member reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13104-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="13104-115">Remarks</span></span>  
 <span data-ttu-id="13104-116">Метод `DefineImportMember` ищет участника, `mbMember`указанного, который определяется в другой `pImport`области, указанной, и извлекает его свойства.</span><span class="sxs-lookup"><span data-stu-id="13104-116">The `DefineImportMember` method looks up the member, specified by `mbMember`, that is defined in another scope, specified by `pImport`, and retrieves its properties.</span></span> <span data-ttu-id="13104-117">Он использует эту информацию для вызова [метода IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) в текущей области для создания ссылки участника.</span><span class="sxs-lookup"><span data-stu-id="13104-117">It uses this information to call the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method in the current scope to create the member reference.</span></span>  
  
 <span data-ttu-id="13104-118">Как правило, перед `DefineImportMember` использованием метода необходимо создать в текущей области ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого члена.</span><span class="sxs-lookup"><span data-stu-id="13104-118">Generally, before you use the `DefineImportMember` method, you must create, in the current scope, a type reference or module reference for the target member's parent class, interface, or module.</span></span> <span data-ttu-id="13104-119">Токен метаданных для этой ссылки `tkParent` затем передается в аргументе.</span><span class="sxs-lookup"><span data-stu-id="13104-119">The metadata token for this reference is then passed in the `tkParent` argument.</span></span> <span data-ttu-id="13104-120">Вам не нужно создавать ссылку на родителей целевого участника, если она будет решена позже компилятором или связующим звеном.</span><span class="sxs-lookup"><span data-stu-id="13104-120">You do not need to create a reference to the target member's parent if it will be resolved later by the compiler or linker.</span></span> <span data-ttu-id="13104-121">Итог:</span><span class="sxs-lookup"><span data-stu-id="13104-121">To summarize:</span></span>  
  
- <span data-ttu-id="13104-122">Если целевой участник является полем или методом, используйте либо [IMetaDataEmit::DefineTypeRefByName,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) либо метод [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) для создания ссылки типа в текущем объеме для родительского класса или родительского интерфейса участника.</span><span class="sxs-lookup"><span data-stu-id="13104-122">If the target member is a field or method, use either the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) or the [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
- <span data-ttu-id="13104-123">Если целевой участник является глобальной переменной или глобальной функцией (т.е. не является членом класса или интерфейса), используйте метод [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) для создания ссылки на модуль в текущей области для родительского модуля участника.</span><span class="sxs-lookup"><span data-stu-id="13104-123">If the target member is a global variable or global function (that is, not a member of a class or interface), use the [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) method to create a module reference, in the current scope, for the member's parent module.</span></span>  
  
- <span data-ttu-id="13104-124">Если родитель целевого участника будет решен позже компилятором `mdTokenNil` `tkParent`или связующим, затем перейдите в .</span><span class="sxs-lookup"><span data-stu-id="13104-124">If the target member's parent will be resolved later by the compiler or linker, then pass `mdTokenNil` in `tkParent`.</span></span> <span data-ttu-id="13104-125">Единственный сценарий, при котором это применимо, это когда глобальная функция или глобальная переменная импортируется из файла .obj, который в конечном итоге будет связан с текущим модулем и объединены метаданными.</span><span class="sxs-lookup"><span data-stu-id="13104-125">The only scenario in which this applies is when a global function or global variable is being imported from a .obj file that will ultimately be linked into the current module and the metadata merged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13104-126">Требования</span><span class="sxs-lookup"><span data-stu-id="13104-126">Requirements</span></span>  
 <span data-ttu-id="13104-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13104-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13104-128">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13104-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13104-129">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13104-129">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13104-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13104-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13104-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13104-131">See also</span></span>

- [<span data-ttu-id="13104-132">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="13104-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="13104-133">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="13104-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
