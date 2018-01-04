---
title: "Метод IMetaDataEmit::SetEventProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8e2089c3f4b4e7677c2ddb9eabc8ee08cfd3695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="2ad1e-102">Метод IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="2ad1e-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="2ad1e-103">Задает или обновляет указанный компонент события, определенного в предыдущем вызове [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ad1e-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ad1e-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="2ad1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ad1e-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="2ad1e-106">[in] Токен события.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="2ad1e-107">[in] Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-107">[in] Event flags.</span></span> <span data-ttu-id="2ad1e-108">Это битовая маска `CorEventAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="2ad1e-109">[in] Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-109">[in] The token for the event class.</span></span> <span data-ttu-id="2ad1e-110">Это может быть вызвано `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="2ad1e-111">[in] Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="2ad1e-112">[in] Метод, используемый для отмены подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="2ad1e-113">[in] Метод, используемый (производным классом), чтобы вызвать это событие.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2ad1e-114">[in] Массив маркеров для других методов, связанный с событием.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="2ad1e-115">Последний элемент массива должен быть `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="2ad1e-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ad1e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="2ad1e-116">Requirements</span></span>  
 <span data-ttu-id="2ad1e-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad1e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad1e-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2ad1e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ad1e-119">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ad1e-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ad1e-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad1e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad1e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2ad1e-121">See Also</span></span>  
 [<span data-ttu-id="2ad1e-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2ad1e-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2ad1e-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2ad1e-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
