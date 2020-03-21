---
title: Метод IMetaDataEmit::SetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177531"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="f780b-102">Метод IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="f780b-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="f780b-103">Устанавливает или обновляет указанную функцию события, определяемую предыдущим вызовом [на IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="f780b-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f780b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f780b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f780b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f780b-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="f780b-106">(в) Токен события.</span><span class="sxs-lookup"><span data-stu-id="f780b-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="f780b-107">(в) Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="f780b-107">[in] Event flags.</span></span> <span data-ttu-id="f780b-108">Это битмаска ценностей. `CorEventAttr`</span><span class="sxs-lookup"><span data-stu-id="f780b-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="f780b-109">(в) Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="f780b-109">[in] The token for the event class.</span></span> <span data-ttu-id="f780b-110">Это либо `mdTypeDef` знак, `mdTypeRef` либо жетон.</span><span class="sxs-lookup"><span data-stu-id="f780b-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="f780b-111">(в) Метод, используемый для подписки на событие, или нулевой.</span><span class="sxs-lookup"><span data-stu-id="f780b-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="f780b-112">(в) Метод, используемый для отписаться от события или свести на нет.</span><span class="sxs-lookup"><span data-stu-id="f780b-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="f780b-113">(в) Метод, используемый (производным классом) для поднятия события.</span><span class="sxs-lookup"><span data-stu-id="f780b-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f780b-114">(в) Массив токенов для других методов, связанных с событием.</span><span class="sxs-lookup"><span data-stu-id="f780b-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="f780b-115">Последний элемент массива `mdMethodDefNil`должен быть.</span><span class="sxs-lookup"><span data-stu-id="f780b-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f780b-116">Требования</span><span class="sxs-lookup"><span data-stu-id="f780b-116">Requirements</span></span>  
 <span data-ttu-id="f780b-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f780b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f780b-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f780b-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f780b-119">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f780b-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f780b-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f780b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f780b-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f780b-121">See also</span></span>

- [<span data-ttu-id="f780b-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f780b-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f780b-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f780b-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
