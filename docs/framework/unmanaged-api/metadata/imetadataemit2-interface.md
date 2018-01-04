---
title: "Интерфейс IMetaDataEmit2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94180a1f844ac43d8a42be59ac4fca807a70ec70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="51dc5-102">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="51dc5-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="51dc5-103">Расширяет [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) интерфейс главным образом для обеспечения возможности работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="51dc5-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51dc5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="51dc5-104">Methods</span></span>  
  
|<span data-ttu-id="51dc5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="51dc5-105">Method</span></span>|<span data-ttu-id="51dc5-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="51dc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51dc5-107">Метод DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="51dc5-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="51dc5-108">Создает определение для параметра универсального типа и возвращает маркер для этого параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="51dc5-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="51dc5-109">Метод DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="51dc5-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="51dc5-110">Создает экземпляр универсального метода и возвращает маркер для определения.</span><span class="sxs-lookup"><span data-stu-id="51dc5-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="51dc5-111">Метод GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="51dc5-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="51dc5-112">Возвращает значение, указывающее, разница в размере данных, необходимых для выражения изменений в текущем сеансе edit-and-continue.</span><span class="sxs-lookup"><span data-stu-id="51dc5-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="51dc5-113">Метод ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="51dc5-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="51dc5-114">Сброс журнала edit and continue и начинает новый сеанс.</span><span class="sxs-lookup"><span data-stu-id="51dc5-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="51dc5-115">Метод SaveDelta</span><span class="sxs-lookup"><span data-stu-id="51dc5-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="51dc5-116">Сохраняет изменения в текущем сеансе edit and continue в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="51dc5-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="51dc5-117">Метод SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="51dc5-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="51dc5-118">Сохраняет изменения в текущем сеансе edit and continue в памяти.</span><span class="sxs-lookup"><span data-stu-id="51dc5-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="51dc5-119">Метод SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="51dc5-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="51dc5-120">Сохраняет изменения в текущем сеансе edit and continue в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="51dc5-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="51dc5-121">Метод SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="51dc5-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="51dc5-122">Задает значения свойств для определения универсальных параметров, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="51dc5-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51dc5-123">Требования</span><span class="sxs-lookup"><span data-stu-id="51dc5-123">Requirements</span></span>  
 <span data-ttu-id="51dc5-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51dc5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51dc5-125">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51dc5-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51dc5-126">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51dc5-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51dc5-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51dc5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51dc5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="51dc5-128">See Also</span></span>  
 [<span data-ttu-id="51dc5-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="51dc5-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="51dc5-130">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="51dc5-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
