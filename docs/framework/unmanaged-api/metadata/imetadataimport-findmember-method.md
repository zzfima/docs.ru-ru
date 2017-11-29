---
title: "Метод IMetaDataImport::FindMember"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a47060575d14e1206e715ea2bfd2ea750bd49c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="508b1-102">Метод IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="508b1-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="508b1-103">Возвращает указатель на MemberDef токен для поля или метода, который заключается в указанном <xref:System.Type> и имеет имя и метаданные указанной подписи.</span><span class="sxs-lookup"><span data-stu-id="508b1-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="508b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="508b1-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="508b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="508b1-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="508b1-106">[in] Токен TypeDef для класса или интерфейса, включающий элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="508b1-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="508b1-107">Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="508b1-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="508b1-108">[in] Имя элемента для поиска.</span><span class="sxs-lookup"><span data-stu-id="508b1-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="508b1-109">[in] Указатель на двоичную подпись метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="508b1-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="508b1-110">[in] Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="508b1-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="508b1-111">[out] Указатель на токен MemberDef сопоставления.</span><span class="sxs-lookup"><span data-stu-id="508b1-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="508b1-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="508b1-112">Remarks</span></span>  
 <span data-ttu-id="508b1-113">Для определения члена с помощью его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="508b1-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="508b1-114">Может существовать несколько членов с тем же именем в классе или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="508b1-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="508b1-115">В этом случае передайте сигнатуру члена, чтобы найти уникальное соответствие.</span><span class="sxs-lookup"><span data-stu-id="508b1-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="508b1-116">Подпись, передаваемый `FindMember` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям.</span><span class="sxs-lookup"><span data-stu-id="508b1-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="508b1-117">Подпись можно внедрить токен, который определяет включающего класса или типа значения.</span><span class="sxs-lookup"><span data-stu-id="508b1-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="508b1-118">Маркер — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="508b1-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="508b1-119">Не удается построить во время выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="508b1-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="508b1-120">`FindMember`находит только те элементы, которые были определены непосредственно в классе или интерфейсе; унаследованные члены не найдена.</span><span class="sxs-lookup"><span data-stu-id="508b1-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="508b1-121">`FindMember`— Это вспомогательный метод.</span><span class="sxs-lookup"><span data-stu-id="508b1-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="508b1-122">Он вызывает [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не удается найти соответствие, `FindMember` вызывает [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="508b1-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="508b1-123">Требования</span><span class="sxs-lookup"><span data-stu-id="508b1-123">Requirements</span></span>  
 <span data-ttu-id="508b1-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="508b1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="508b1-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="508b1-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="508b1-126">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="508b1-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="508b1-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="508b1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508b1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="508b1-128">See Also</span></span>  
 [<span data-ttu-id="508b1-129">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="508b1-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="508b1-130">IMetaDataImport2-интерфейс</span><span class="sxs-lookup"><span data-stu-id="508b1-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
