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
ms.openlocfilehash: 46ee8c62861a62ac044f295f7da082756d87347b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="e9d8f-102">Метод IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="e9d8f-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="e9d8f-103">Перечисляет токены MemberDef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9d8f-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9d8f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9d8f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e9d8f-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e9d8f-107">[in] Токен TypeDef, представляющий тип, членами которой являются перечисления.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="e9d8f-108">[out] Массив, используемый для хранения токены MemberDef.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e9d8f-109">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e9d8f-110">[out] Фактическое число токены MemberDef, возвращаемых в `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9d8f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e9d8f-111">Return Value</span></span>  
  
|<span data-ttu-id="e9d8f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9d8f-112">HRESULT</span></span>|<span data-ttu-id="e9d8f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e9d8f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e9d8f-114">`EnumMembers` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e9d8f-115">Существуют маркеры MemberDef для перечисления отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="e9d8f-116">В этом случае `pcTokens` равно нулю.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d8f-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9d8f-117">Remarks</span></span>  
 <span data-ttu-id="e9d8f-118">При перечислении коллекций членов для класса `EnumMembers` возвращает только члены, определенные непосредственно в классе.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="e9d8f-119">Он не возвращает члены, которые наследует класс, даже если класс предоставляет реализацию этих унаследованных членов.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="e9d8f-120">Для перечисления унаследованных членов, вызывающий объект явно необходимо пройти в цепочке наследования.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="e9d8f-121">Обратите внимание, что правила для цепи наследования может меняться в зависимости от языка или компилятора, выдавшего исходные метаданные.</span><span class="sxs-lookup"><span data-stu-id="e9d8f-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d8f-122">Требования</span><span class="sxs-lookup"><span data-stu-id="e9d8f-122">Requirements</span></span>  
 <span data-ttu-id="e9d8f-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d8f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d8f-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9d8f-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9d8f-125">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9d8f-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d8f-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d8f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d8f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e9d8f-127">See Also</span></span>  
 [<span data-ttu-id="e9d8f-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e9d8f-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e9d8f-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e9d8f-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
