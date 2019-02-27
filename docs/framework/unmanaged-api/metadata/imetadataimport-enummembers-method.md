---
title: Метод IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de4bf2cf647682062fbacb4484ffae905d1b7995
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835373"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="c2734-102">Метод IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="c2734-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="c2734-103">Перечисляет токены MemberDef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="c2734-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2734-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2734-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2734-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2734-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c2734-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="c2734-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="c2734-107">[in] Токен TypeDef, представляющий тип, члены которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="c2734-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="c2734-108">[out] Массив, используемый для хранения токены MemberDef.</span><span class="sxs-lookup"><span data-stu-id="c2734-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c2734-109">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="c2734-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c2734-110">[out] Фактическое количество возвращаемых в токены MemberDef `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="c2734-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2734-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c2734-111">Return Value</span></span>  
  
|<span data-ttu-id="c2734-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2734-112">HRESULT</span></span>|<span data-ttu-id="c2734-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="c2734-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c2734-114">`EnumMembers` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="c2734-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c2734-115">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="c2734-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="c2734-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c2734-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2734-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2734-117">Remarks</span></span>  
 <span data-ttu-id="c2734-118">При перечислении коллекций членов для класса, `EnumMembers` возвращает только члены (поля и методы, но **не** свойств или событий) определенные непосредственно в классе.</span><span class="sxs-lookup"><span data-stu-id="c2734-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="c2734-119">Он не возвращает элементы, класс наследуется, даже если этот класс предоставляет реализацию для этих унаследованных членов.</span><span class="sxs-lookup"><span data-stu-id="c2734-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="c2734-120">Чтобы перечислить унаследованные члены, вызывающий объект явным образом необходимо пройти по цепочке наследования.</span><span class="sxs-lookup"><span data-stu-id="c2734-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="c2734-121">Обратите внимание, что правила для цепи наследования может меняться в зависимости от языка или компилятора, выдавшего исходные метаданные.</span><span class="sxs-lookup"><span data-stu-id="c2734-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="c2734-122">Свойства и события не перечисляет `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="c2734-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="c2734-123">Чтобы перечислить их, используйте [EnumProperties](imetadataimport-enumproperties-method.md) или [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="c2734-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="c2734-124">Требования</span><span class="sxs-lookup"><span data-stu-id="c2734-124">Requirements</span></span>  
 <span data-ttu-id="c2734-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2734-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2734-126">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2734-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2734-127">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2734-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2734-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2734-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2734-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c2734-129">See also</span></span>
- [<span data-ttu-id="c2734-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c2734-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c2734-131">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c2734-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
