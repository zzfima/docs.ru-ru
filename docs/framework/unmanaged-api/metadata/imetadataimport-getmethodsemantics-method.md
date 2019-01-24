---
title: Метод IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a12310f1281da99706589894a4793c2a28c5b938
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745996"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="69dc1-102">Метод IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="69dc1-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="69dc1-103">Получает флаги, указывающее на соотношение метод ссылается указанный токен MethodDef и свойства и события ссылается указанный EventProp маркер.</span><span class="sxs-lookup"><span data-stu-id="69dc1-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69dc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69dc1-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69dc1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69dc1-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="69dc1-106">[in] Токен MethodDef, представляющий метод, чтобы получить сведения о семантических роли.</span><span class="sxs-lookup"><span data-stu-id="69dc1-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="69dc1-107">[in] Токен, представляющий свойства и события, для которого необходимо получить роль метода.</span><span class="sxs-lookup"><span data-stu-id="69dc1-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="69dc1-108">[out] Указатель на связанную семантику флаги.</span><span class="sxs-lookup"><span data-stu-id="69dc1-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="69dc1-109">Это значение является битовой [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="69dc1-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69dc1-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="69dc1-110">Remarks</span></span>  
 <span data-ttu-id="69dc1-111">[IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) метод задает флаги семантики метода.</span><span class="sxs-lookup"><span data-stu-id="69dc1-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69dc1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="69dc1-112">Requirements</span></span>  
 <span data-ttu-id="69dc1-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69dc1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69dc1-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69dc1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69dc1-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69dc1-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69dc1-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69dc1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69dc1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="69dc1-117">See also</span></span>
- [<span data-ttu-id="69dc1-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="69dc1-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="69dc1-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="69dc1-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
