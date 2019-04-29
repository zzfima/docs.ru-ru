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
ms.openlocfilehash: 57ddbd8c6935f2c0275c132e30ea175c6f198fac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777706"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="b7d22-102">Метод IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="b7d22-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="b7d22-103">Получает флаги, указывающее на соотношение метод ссылается указанный токен MethodDef и свойства и события ссылается указанный EventProp маркер.</span><span class="sxs-lookup"><span data-stu-id="b7d22-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7d22-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7d22-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7d22-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="b7d22-106">[in] Токен MethodDef, представляющий метод, чтобы получить сведения о семантических роли.</span><span class="sxs-lookup"><span data-stu-id="b7d22-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="b7d22-107">[in] Токен, представляющий свойства и события, для которого необходимо получить роль метода.</span><span class="sxs-lookup"><span data-stu-id="b7d22-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="b7d22-108">[out] Указатель на связанную семантику флаги.</span><span class="sxs-lookup"><span data-stu-id="b7d22-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="b7d22-109">Это значение является битовой [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="b7d22-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7d22-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7d22-110">Remarks</span></span>  
 <span data-ttu-id="b7d22-111">[IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) метод задает флаги семантики метода.</span><span class="sxs-lookup"><span data-stu-id="b7d22-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d22-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b7d22-112">Requirements</span></span>  
 <span data-ttu-id="b7d22-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d22-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d22-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7d22-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7d22-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7d22-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7d22-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d22-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d22-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b7d22-117">See also</span></span>

- [<span data-ttu-id="b7d22-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b7d22-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b7d22-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b7d22-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
