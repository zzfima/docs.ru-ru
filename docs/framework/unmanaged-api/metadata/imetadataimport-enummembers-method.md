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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175490"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="8bac1-102">Метод IMetaDataImport::EnumMembers</span><span class="sxs-lookup"><span data-stu-id="8bac1-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="8bac1-103">Перечисляет токены MemberDef, представляющие члены указанного типа.</span><span class="sxs-lookup"><span data-stu-id="8bac1-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bac1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bac1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bac1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bac1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8bac1-106">(в, вне) Указатель на регистратор.</span><span class="sxs-lookup"><span data-stu-id="8bac1-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="8bac1-107">(в) Токен TypeDef, представляющий тип, члены которого должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="8bac1-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="8bac1-108">(ваут) Массив, используемый для хранения токенов MemberDef.</span><span class="sxs-lookup"><span data-stu-id="8bac1-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8bac1-109">[in] Максимальный размер массива `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="8bac1-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8bac1-110">(ваут) Фактическое количество токенов MemberDef `rMembers`возвращено в .</span><span class="sxs-lookup"><span data-stu-id="8bac1-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bac1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8bac1-111">Return Value</span></span>  
  
|<span data-ttu-id="8bac1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bac1-112">HRESULT</span></span>|<span data-ttu-id="8bac1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8bac1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8bac1-114">`EnumMembers`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="8bac1-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8bac1-115">Нет токенов MemberDef для перечисления.</span><span class="sxs-lookup"><span data-stu-id="8bac1-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="8bac1-116">В этом `pcTokens` случае, равна нулю.</span><span class="sxs-lookup"><span data-stu-id="8bac1-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bac1-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="8bac1-117">Remarks</span></span>  
 <span data-ttu-id="8bac1-118">При перечислении коллекций участников `EnumMembers` для класса возвращается только участники (поля и методы, но **не** свойства или события), определенные непосредственно на классе.</span><span class="sxs-lookup"><span data-stu-id="8bac1-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="8bac1-119">Он не возвращает членов, которые класс наследует, даже если класс обеспечивает реализацию для этих унаследованных членов.</span><span class="sxs-lookup"><span data-stu-id="8bac1-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="8bac1-120">Чтобы перечислить наследственных членов, абонент должен явно ходить цепи наследования.</span><span class="sxs-lookup"><span data-stu-id="8bac1-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="8bac1-121">Обратите внимание, что правила для цепочки наследования могут варьироваться в зависимости от языка или компилятора, испускающего исходные метаданные.</span><span class="sxs-lookup"><span data-stu-id="8bac1-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="8bac1-122">Свойства и события не перечисляются `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="8bac1-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="8bac1-123">Чтобы перечислить их, используйте [EnumProperties](imetadataimport-enumproperties-method.md) или [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="8bac1-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8bac1-124">Требования</span><span class="sxs-lookup"><span data-stu-id="8bac1-124">Requirements</span></span>  
 <span data-ttu-id="8bac1-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bac1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bac1-126">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bac1-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bac1-127">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bac1-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bac1-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bac1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bac1-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8bac1-129">See also</span></span>

- [<span data-ttu-id="8bac1-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8bac1-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8bac1-131">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8bac1-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
