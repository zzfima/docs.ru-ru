---
title: Метод IMetaDataEmit::DefineCustomAttribute
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175893"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="b09ac-102">Метод IMetaDataEmit::DefineCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="b09ac-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="b09ac-103">Создает определение для пользовательского атрибута с указанной подписью метаданных, который будет прикреплен к указанному объекту, и получает маркер к этому пользовательскому определению атрибута.</span><span class="sxs-lookup"><span data-stu-id="b09ac-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b09ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b09ac-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b09ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b09ac-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="b09ac-106">(в) Токен для элемента владельца.</span><span class="sxs-lookup"><span data-stu-id="b09ac-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b09ac-107">(в) Токен, идентифицирует пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="b09ac-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="b09ac-108">(в) Указатель на пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="b09ac-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="b09ac-109">(в) Количество байтов `pCustomAttribute`в .</span><span class="sxs-lookup"><span data-stu-id="b09ac-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="b09ac-110">(ваут) Назначенный `mdCustomAttribute` маркер.</span><span class="sxs-lookup"><span data-stu-id="b09ac-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b09ac-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b09ac-111">Requirements</span></span>  
 <span data-ttu-id="b09ac-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b09ac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b09ac-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b09ac-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b09ac-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b09ac-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b09ac-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b09ac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09ac-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b09ac-116">See also</span></span>

- [<span data-ttu-id="b09ac-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b09ac-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b09ac-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b09ac-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
