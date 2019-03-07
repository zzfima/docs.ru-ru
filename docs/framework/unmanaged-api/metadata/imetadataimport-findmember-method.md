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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 777d7bf51db3e6984f30e31c46ac115301d13faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478977"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="9d9d9-102">Метод IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="9d9d9-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="9d9d9-103">Возвращает указатель на MemberDef токен для поля или метода, который заключен заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d9d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d9d9-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d9d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d9d9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9d9d9-106">[in] Токен TypeDef для класса или интерфейса, который окружает элемент для поиска.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="9d9d9-107">Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="9d9d9-108">[in] Имя элемента для поиска.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9d9d9-109">[in] Указатель на двоичную подпись метаданных элемента.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9d9d9-110">[in] Размер в байтах `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="9d9d9-111">[out] Указатель на токен MemberDef сопоставления.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d9d9-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d9d9-112">Remarks</span></span>  
 <span data-ttu-id="9d9d9-113">Для определения члена с помощью его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="9d9d9-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="9d9d9-114">Может существовать несколько членов с одинаковыми именами в классе или интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="9d9d9-115">В этом случае следует передайте сигнатуре члена, чтобы найти уникальное соответствие.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="9d9d9-116">Подпись передается `FindMember` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="9d9d9-117">Подписи можно внедрить токен, который определяет включающего класса или типа значения.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="9d9d9-118">Маркер — это индекс в локальной таблице TypeDef.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="9d9d9-119">Не удается построить выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="9d9d9-120">`FindMember` находит только те элементы, которые были определены непосредственно в классе или интерфейсе; унаследованные члены не найден.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d9d9-121">`FindMember` — Это вспомогательный метод.</span><span class="sxs-lookup"><span data-stu-id="9d9d9-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="9d9d9-122">Он вызывает [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не удается найти соответствие, `FindMember` затем вызывает [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="9d9d9-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d9d9-123">Требования</span><span class="sxs-lookup"><span data-stu-id="9d9d9-123">Requirements</span></span>  
 <span data-ttu-id="9d9d9-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d9d9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d9d9-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d9d9-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d9d9-126">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d9d9-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d9d9-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d9d9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d9d9-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9d9d9-128">See also</span></span>
- [<span data-ttu-id="9d9d9-129">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9d9d9-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9d9d9-130">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9d9d9-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
