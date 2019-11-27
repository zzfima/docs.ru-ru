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
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432563"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="f56b9-102">Метод IMetaDataEmit::DefineEvent</span><span class="sxs-lookup"><span data-stu-id="f56b9-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="f56b9-103">Создает определение для события с указанной сигнатурой метаданных и получает маркер для этого определения события.</span><span class="sxs-lookup"><span data-stu-id="f56b9-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f56b9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f56b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f56b9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f56b9-106">окне Токен для целевого класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f56b9-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="f56b9-107">Это либо маркер `mdTypeDef`, либо `mdTypeDefNil`.</span><span class="sxs-lookup"><span data-stu-id="f56b9-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="f56b9-108">окне Имя события.</span><span class="sxs-lookup"><span data-stu-id="f56b9-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="f56b9-109">окне Флаги событий.</span><span class="sxs-lookup"><span data-stu-id="f56b9-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="f56b9-110">окне Токен для класса событий.</span><span class="sxs-lookup"><span data-stu-id="f56b9-110">[in] The token for the event class.</span></span> <span data-ttu-id="f56b9-111">Это `mdTypeDef`, `mdTypeRef`или токен `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="f56b9-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="f56b9-112">окне Метод, используемый для подписки на событие, или значение null.</span><span class="sxs-lookup"><span data-stu-id="f56b9-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="f56b9-113">окне Метод, используемый для отмены подписки на событие или значение null.</span><span class="sxs-lookup"><span data-stu-id="f56b9-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="f56b9-114">окне Метод, используемый (производным классом) для вызова события.</span><span class="sxs-lookup"><span data-stu-id="f56b9-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f56b9-115">окне Массив токенов для других методов, связанных с событием.</span><span class="sxs-lookup"><span data-stu-id="f56b9-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="f56b9-116">Массив завершается маркером `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="f56b9-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="f56b9-117">заполняет Маркер метаданных, назначенный событию.</span><span class="sxs-lookup"><span data-stu-id="f56b9-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56b9-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f56b9-118">Requirements</span></span>  
 <span data-ttu-id="f56b9-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f56b9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56b9-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f56b9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f56b9-121">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f56b9-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f56b9-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56b9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56b9-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f56b9-123">See also</span></span>

- [<span data-ttu-id="f56b9-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f56b9-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f56b9-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f56b9-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
