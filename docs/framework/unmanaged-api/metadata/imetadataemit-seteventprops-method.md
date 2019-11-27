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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450316"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="cbe84-102">Метод IMetaDataEmit::SetEventProps</span><span class="sxs-lookup"><span data-stu-id="cbe84-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="cbe84-103">Задает или обновляет указанную функцию события, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинивент](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="cbe84-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbe84-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cbe84-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbe84-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="cbe84-106">окне Токен события.</span><span class="sxs-lookup"><span data-stu-id="cbe84-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="cbe84-107">окне Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="cbe84-107">[in] Event flags.</span></span> <span data-ttu-id="cbe84-108">Это битовая маска `CorEventAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="cbe84-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="cbe84-109">окне Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="cbe84-109">[in] The token for the event class.</span></span> <span data-ttu-id="cbe84-110">Это либо `mdTypeDef`, либо маркер `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="cbe84-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="cbe84-111">окне Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="cbe84-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="cbe84-112">окне Метод, используемый для отмены подписки на событие или значение null.</span><span class="sxs-lookup"><span data-stu-id="cbe84-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="cbe84-113">окне Метод, используемый (производным классом) для вызова события.</span><span class="sxs-lookup"><span data-stu-id="cbe84-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="cbe84-114">окне Массив токенов для других методов, связанных с событием.</span><span class="sxs-lookup"><span data-stu-id="cbe84-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="cbe84-115">Последний элемент массива должен быть `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="cbe84-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe84-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cbe84-116">Requirements</span></span>  
 <span data-ttu-id="cbe84-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbe84-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe84-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="cbe84-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbe84-119">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cbe84-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbe84-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe84-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe84-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="cbe84-121">See also</span></span>

- [<span data-ttu-id="cbe84-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cbe84-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cbe84-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cbe84-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
