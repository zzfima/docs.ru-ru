---
title: Метод IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177285"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="8677d-102">Метод IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="8677d-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="8677d-103">Получает указатель на токен MemberDef для поля или метода, который прилагается указанным <xref:System.Type> и который имеет указанное имя и подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="8677d-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8677d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8677d-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8677d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8677d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8677d-106">(в) Токен TypeDef для класса или интерфейса, который примыкает к поиску участника.</span><span class="sxs-lookup"><span data-stu-id="8677d-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="8677d-107">Если это `mdTokenNil`значение, то поиск выполняется для глобально-переменной или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="8677d-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="8677d-108">(в) Имя участника для поиска.</span><span class="sxs-lookup"><span data-stu-id="8677d-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8677d-109">(в) Указатель на двоичную подпись метаданных участника.</span><span class="sxs-lookup"><span data-stu-id="8677d-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8677d-110">(в) Размер байтов `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="8677d-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="8677d-111">(ваут) Указатель на соответствующий токен MemberDef.</span><span class="sxs-lookup"><span data-stu-id="8677d-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8677d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="8677d-112">Remarks</span></span>  
 <span data-ttu-id="8677d-113">Вы указываете участника, используя его`td`прилагающий`szName`класс или интерфейс (), его имя (), и по желанию его подпись ().`pvSigBlob`</span><span class="sxs-lookup"><span data-stu-id="8677d-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="8677d-114">В классе или интерфейсе может быть несколько членов с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="8677d-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="8677d-115">В этом случае, пройти подпись члена, чтобы найти уникальный матч.</span><span class="sxs-lookup"><span data-stu-id="8677d-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="8677d-116">Подпись, `FindMember` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="8677d-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="8677d-117">Подпись может вставлять маркер, который определяет класс или тип значения.</span><span class="sxs-lookup"><span data-stu-id="8677d-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="8677d-118">Токен — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="8677d-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="8677d-119">Нельзя создавать подпись времени выполнения вне контекста текущей области и использовать `FindMember`эту подпись в качестве ввода для ввода.</span><span class="sxs-lookup"><span data-stu-id="8677d-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="8677d-120">`FindMember`находит только участников, которые были определены непосредственно в классе или интерфейсе; он не находит наследственных членов.</span><span class="sxs-lookup"><span data-stu-id="8677d-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8677d-121">`FindMember`является методом помощника.</span><span class="sxs-lookup"><span data-stu-id="8677d-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="8677d-122">Он называет [IMetaDataИмпорт::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); если этот вызов не находит `FindMember` совпадения, то звонит [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="8677d-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8677d-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8677d-123">Requirements</span></span>  
 <span data-ttu-id="8677d-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8677d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8677d-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8677d-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8677d-126">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8677d-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8677d-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8677d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8677d-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8677d-128">See also</span></span>

- [<span data-ttu-id="8677d-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8677d-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8677d-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8677d-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
