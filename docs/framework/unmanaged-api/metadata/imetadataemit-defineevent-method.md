---
title: Метод IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175854"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="089d8-102">Метод IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="089d8-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="089d8-103">Создает определение события с указанной подписью метаданных и получает маркер к определению этого события.</span><span class="sxs-lookup"><span data-stu-id="089d8-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="089d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="089d8-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="089d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="089d8-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="089d8-106">(в) Токен для целевого класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="089d8-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="089d8-107">Это либо `mdTypeDef` знак, либо `mdTypeDefNil` маркер.</span><span class="sxs-lookup"><span data-stu-id="089d8-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="089d8-108">[in] Имя события.</span><span class="sxs-lookup"><span data-stu-id="089d8-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="089d8-109">(в) Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="089d8-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="089d8-110">(в) Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="089d8-110">[in] The token for the event class.</span></span> <span data-ttu-id="089d8-111">`mdTypeDef`Это, a `mdTypeRef`, или `mdTokenNil` маркер.</span><span class="sxs-lookup"><span data-stu-id="089d8-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="089d8-112">(в) Метод, используемый для подписки на событие, или нулевой.</span><span class="sxs-lookup"><span data-stu-id="089d8-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="089d8-113">(в) Метод, используемый для отписаться от события или свести на нет.</span><span class="sxs-lookup"><span data-stu-id="089d8-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="089d8-114">(в) Метод, используемый (производным классом) для поднятия события.</span><span class="sxs-lookup"><span data-stu-id="089d8-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="089d8-115">(в) Массив токенов для других методов, связанных с событием.</span><span class="sxs-lookup"><span data-stu-id="089d8-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="089d8-116">Массив завершается маркером. `mdMethodDefNil`</span><span class="sxs-lookup"><span data-stu-id="089d8-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="089d8-117">(ваут) Токен метаданных, назначенный событию.</span><span class="sxs-lookup"><span data-stu-id="089d8-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="089d8-118">Требования</span><span class="sxs-lookup"><span data-stu-id="089d8-118">Requirements</span></span>  
 <span data-ttu-id="089d8-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="089d8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="089d8-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="089d8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="089d8-121">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="089d8-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="089d8-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="089d8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="089d8-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="089d8-123">See also</span></span>

- [<span data-ttu-id="089d8-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="089d8-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="089d8-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="089d8-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
