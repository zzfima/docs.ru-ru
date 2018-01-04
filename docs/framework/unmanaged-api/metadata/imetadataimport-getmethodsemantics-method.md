---
title: "Метод IMetaDataImport::GetMethodSemantics"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f8921c4f6a676c9647d4e8907a22f0d68b0b359
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="19f32-102">Метод IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="19f32-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="19f32-103">Получает флаги, указывающие на связь между методом, ссылается заданный токен MethodDef и свойства и события ссылается указанный EventProp маркер.</span><span class="sxs-lookup"><span data-stu-id="19f32-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19f32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19f32-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19f32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="19f32-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="19f32-106">[in] Токен MethodDef, предоставляющий метод, чтобы получить сведения о семантических роли.</span><span class="sxs-lookup"><span data-stu-id="19f32-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="19f32-107">[in] Токен, представляющий свойства и события, для которого требуется получить метод роли.</span><span class="sxs-lookup"><span data-stu-id="19f32-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="19f32-108">[out] Указатель на связанную семантику флаги.</span><span class="sxs-lookup"><span data-stu-id="19f32-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="19f32-109">Это значение является битовой [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="19f32-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19f32-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="19f32-110">Remarks</span></span>  
 <span data-ttu-id="19f32-111">[IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) метод задает метод флагов семантики.</span><span class="sxs-lookup"><span data-stu-id="19f32-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19f32-112">Требования</span><span class="sxs-lookup"><span data-stu-id="19f32-112">Requirements</span></span>  
 <span data-ttu-id="19f32-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19f32-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f32-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="19f32-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19f32-115">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19f32-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19f32-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19f32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f32-117">См. также</span><span class="sxs-lookup"><span data-stu-id="19f32-117">See Also</span></span>  
 [<span data-ttu-id="19f32-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="19f32-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="19f32-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="19f32-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
