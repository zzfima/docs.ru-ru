---
title: "Метод IMetaDataImport::FindMemberRef"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a94fb09e1ff62abac9dd716257ba75542453707e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="3745f-102">Метод IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="3745f-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="3745f-103">Возвращает указатель на токен MemberRef для члена, то есть ссылки, заключенных в указанный <xref:System.Type> и имеет имя и метаданные указанной подписи.</span><span class="sxs-lookup"><span data-stu-id="3745f-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3745f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3745f-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3745f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3745f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="3745f-106">[in] Лексема TypeRef для класса или интерфейса, включающий ссылку на элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="3745f-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="3745f-107">Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или ссылка глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="3745f-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="3745f-108">[in] Имя члена ссылки для поиска.</span><span class="sxs-lookup"><span data-stu-id="3745f-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="3745f-109">[in] Указатель на двоичную подпись метаданных для ссылки на член.</span><span class="sxs-lookup"><span data-stu-id="3745f-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3745f-110">[in] Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="3745f-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="3745f-111">[out] Указатель на токен MemberRef сопоставления.</span><span class="sxs-lookup"><span data-stu-id="3745f-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3745f-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="3745f-112">Remarks</span></span>  
 <span data-ttu-id="3745f-113">Для определения члена с помощью его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="3745f-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="3745f-114">Подпись, передаваемый `FindMemberRef` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям.</span><span class="sxs-lookup"><span data-stu-id="3745f-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="3745f-115">Подпись можно внедрить токен, который определяет включающего класса или типа значения.</span><span class="sxs-lookup"><span data-stu-id="3745f-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="3745f-116">Маркер — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="3745f-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="3745f-117">Не удается построить во время выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="3745f-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="3745f-118">`FindMemberRef`находит только ссылок на элементы, определенные непосредственно в классе или интерфейсе. не удается найти ссылок на унаследованные члены.</span><span class="sxs-lookup"><span data-stu-id="3745f-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3745f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3745f-119">Requirements</span></span>  
 <span data-ttu-id="3745f-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3745f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3745f-121">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3745f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3745f-122">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3745f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3745f-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3745f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3745f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3745f-124">See Also</span></span>  
 [<span data-ttu-id="3745f-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3745f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="3745f-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3745f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
