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
ms.openlocfilehash: 88b8f874400d68110fa5e8fb66ca910b8e7231e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645968"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="46656-102">Метод IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="46656-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="46656-103">Перечисляет токены MemberDef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="46656-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46656-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46656-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46656-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="46656-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="46656-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="46656-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="46656-107">[in] Токен TypeDef, представляющий тип, члены которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="46656-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="46656-108">[out] Массив, используемый для хранения токены MemberDef.</span><span class="sxs-lookup"><span data-stu-id="46656-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="46656-109">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="46656-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="46656-110">[out] Фактическое количество возвращаемых в токены MemberDef `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="46656-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46656-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46656-111">Return Value</span></span>  
  
|<span data-ttu-id="46656-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46656-112">HRESULT</span></span>|<span data-ttu-id="46656-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="46656-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="46656-114">`EnumMembers` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="46656-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="46656-115">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="46656-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="46656-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="46656-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46656-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="46656-117">Remarks</span></span>  
 <span data-ttu-id="46656-118">При перечислении коллекций членов для класса, `EnumMembers` возвращает только те члены, определенные непосредственно в классе.</span><span class="sxs-lookup"><span data-stu-id="46656-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="46656-119">Он не возвращает элементы, класс наследуется, даже если этот класс предоставляет реализацию для этих унаследованных членов.</span><span class="sxs-lookup"><span data-stu-id="46656-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="46656-120">Чтобы перечислить унаследованные члены, вызывающий объект явным образом необходимо пройти по цепочке наследования.</span><span class="sxs-lookup"><span data-stu-id="46656-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="46656-121">Обратите внимание, что правила для цепи наследования может меняться в зависимости от языка или компилятора, выдавшего исходные метаданные.</span><span class="sxs-lookup"><span data-stu-id="46656-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46656-122">Требования</span><span class="sxs-lookup"><span data-stu-id="46656-122">Requirements</span></span>  
 <span data-ttu-id="46656-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46656-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46656-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="46656-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46656-125">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46656-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46656-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46656-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46656-127">См. также</span><span class="sxs-lookup"><span data-stu-id="46656-127">See also</span></span>
- [<span data-ttu-id="46656-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="46656-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="46656-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="46656-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
