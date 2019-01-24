---
title: Интерфейс IMetaDataEmit2
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e0477adb4958a53289cd0a64f39259403fa7dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656938"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="b3a7b-102">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b3a7b-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="b3a7b-103">Расширяет [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейс, главным образом, чтобы предоставить возможность работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3a7b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b3a7b-104">Methods</span></span>  
  
|<span data-ttu-id="b3a7b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b3a7b-105">Method</span></span>|<span data-ttu-id="b3a7b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="b3a7b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3a7b-107">Метод DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="b3a7b-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="b3a7b-108">Создает определение для параметра универсального типа и возвращает маркер для этого параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="b3a7b-109">Метод DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="b3a7b-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="b3a7b-110">Создает экземпляр универсального метода и возвращает маркер для определения.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="b3a7b-111">Метод GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="b3a7b-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="b3a7b-112">Получает значение, указывающее, разница в размере данных, который необходим для выражения изменений в текущем сеансе, изменить и продолжить.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="b3a7b-113">Метод ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="b3a7b-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="b3a7b-114">Сбрасывает журнал изменить и продолжить и начинает новый сеанс.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="b3a7b-115">Метод SaveDelta</span><span class="sxs-lookup"><span data-stu-id="b3a7b-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="b3a7b-116">Сохраняет изменения в текущем сеансе, изменить и продолжить в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="b3a7b-117">Метод SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="b3a7b-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="b3a7b-118">Сохраняет изменения в текущем сеансе, изменить и продолжить в памяти.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="b3a7b-119">Метод SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="b3a7b-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="b3a7b-120">Сохраняет изменения в текущем сеансе, изменить и продолжить в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="b3a7b-121">Метод SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="b3a7b-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="b3a7b-122">Задает значения свойств для определения универсального параметра, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3a7b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="b3a7b-123">Requirements</span></span>  
 <span data-ttu-id="b3a7b-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3a7b-125">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3a7b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3a7b-126">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3a7b-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3a7b-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3a7b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a7b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b3a7b-128">See also</span></span>
- [<span data-ttu-id="b3a7b-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="b3a7b-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b3a7b-130">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b3a7b-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
