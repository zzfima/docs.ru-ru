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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42dc78ff3c58b67801cd99512781d8c8509dd272
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447344"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="a49fc-102">Метод IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="a49fc-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="a49fc-103">Задает или обновляет указанный компонент события, определенного в предыдущем вызове [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="a49fc-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49fc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a49fc-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="a49fc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a49fc-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="a49fc-106">[in] Токен события.</span><span class="sxs-lookup"><span data-stu-id="a49fc-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="a49fc-107">[in] Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="a49fc-107">[in] Event flags.</span></span> <span data-ttu-id="a49fc-108">Это битовая маска `CorEventAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="a49fc-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="a49fc-109">[in] Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="a49fc-109">[in] The token for the event class.</span></span> <span data-ttu-id="a49fc-110">Это может быть вызвано `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="a49fc-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="a49fc-111">[in] Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="a49fc-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="a49fc-112">[in] Метод, используемый для отмены подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="a49fc-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="a49fc-113">[in] Метод, используемый (производным классом), чтобы вызвать это событие.</span><span class="sxs-lookup"><span data-stu-id="a49fc-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="a49fc-114">[in] Массив маркеров для других методов, связанный с событием.</span><span class="sxs-lookup"><span data-stu-id="a49fc-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="a49fc-115">Последний элемент массива должен быть `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="a49fc-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a49fc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="a49fc-116">Requirements</span></span>  
 <span data-ttu-id="a49fc-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a49fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a49fc-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a49fc-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a49fc-119">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a49fc-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a49fc-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a49fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49fc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a49fc-121">See Also</span></span>  
 [<span data-ttu-id="a49fc-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a49fc-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a49fc-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a49fc-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
