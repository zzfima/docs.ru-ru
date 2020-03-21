---
title: Метод IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175425"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="b4bf4-102">Метод IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="b4bf4-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="b4bf4-103">Получает указатель на токен MemberRef для ссылки участника, <xref:System.Type> которая прилагается указанным и имеет указанное имя и подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4bf4-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4bf4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4bf4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b4bf4-106">(в) Токен TypeRef для класса или интерфейса, который примыкает к поиску участника.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="b4bf4-107">Если это `mdTokenNil`значение, то поиск выполняется для глобальной переменной или глобальной функциональной ссылки.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4bf4-108">(в) Имя участника ссылки на поиск.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b4bf4-109">(в) Указатель на двоичную подпись метаданных ссылки участника.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b4bf4-110">(в) Размер байтов `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="b4bf4-111">(ваут) Указатель на соответствующий токен MemberRef.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4bf4-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="b4bf4-112">Remarks</span></span>  
 <span data-ttu-id="b4bf4-113">Вы указываете участника, используя его`td`прилагающий`szName`класс или интерфейс (), его имя (), и по желанию его подпись ().`pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="b4bf4-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="b4bf4-114">Подпись, `FindMemberRef` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="b4bf4-115">Подпись может вставлять маркер, который определяет класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="b4bf4-116">Токен — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="b4bf4-117">Нельзя создавать подпись времени выполнения вне контекста текущей области и `FindMemberRef`использовать эту подпись в качестве ввода.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="b4bf4-118">`FindMemberRef`находит только ссылки членов, которые были определены непосредственно в классе или интерфейсе; он не находит унаследованных ссылок членов.</span><span class="sxs-lookup"><span data-stu-id="b4bf4-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4bf4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="b4bf4-119">Requirements</span></span>  
 <span data-ttu-id="b4bf4-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4bf4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4bf4-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4bf4-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4bf4-122">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4bf4-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4bf4-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4bf4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4bf4-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4bf4-124">See also</span></span>

- [<span data-ttu-id="b4bf4-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b4bf4-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4bf4-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b4bf4-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
