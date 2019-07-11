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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba35cd678d88389854ca2e866020ea3a9364c923
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777664"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="e5500-102">Метод IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="e5500-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="e5500-103">Создает определение события с заданной подписью метаданных и получает маркер для определения событий.</span><span class="sxs-lookup"><span data-stu-id="e5500-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5500-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5500-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e5500-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5500-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e5500-106">[in] Токен для целевого класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e5500-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="e5500-107">Это может быть либо `mdTypeDef` или `mdTypeDefNil` токена.</span><span class="sxs-lookup"><span data-stu-id="e5500-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="e5500-108">[in] Имя события.</span><span class="sxs-lookup"><span data-stu-id="e5500-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="e5500-109">[in] Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="e5500-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="e5500-110">[in] Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="e5500-110">[in] The token for the event class.</span></span> <span data-ttu-id="e5500-111">Это `mdTypeDef`, `mdTypeRef`, или `mdTokenNil` токена.</span><span class="sxs-lookup"><span data-stu-id="e5500-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="e5500-112">[in] Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="e5500-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="e5500-113">[in] Метод, используемый для отказа от подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="e5500-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="e5500-114">[in] Метод, используемый (с помощью производного класса) для вызова события.</span><span class="sxs-lookup"><span data-stu-id="e5500-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e5500-115">[in] Массив маркеров для других методов, связанный с событием.</span><span class="sxs-lookup"><span data-stu-id="e5500-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="e5500-116">Массив прерывается с выдачей `mdMethodDefNil` токена.</span><span class="sxs-lookup"><span data-stu-id="e5500-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="e5500-117">[out] Токен метаданных, присвоенная событию.</span><span class="sxs-lookup"><span data-stu-id="e5500-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5500-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e5500-118">Requirements</span></span>  
 <span data-ttu-id="e5500-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5500-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5500-120">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5500-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5500-121">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5500-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5500-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5500-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5500-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e5500-123">See also</span></span>

- [<span data-ttu-id="e5500-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e5500-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e5500-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e5500-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
