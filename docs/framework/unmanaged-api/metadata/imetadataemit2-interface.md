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
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447914"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="01205-102">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="01205-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="01205-103">Расширяет интерфейс [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) в основном, чтобы обеспечить возможность работы с универсальными типами.</span><span class="sxs-lookup"><span data-stu-id="01205-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01205-104">Методы</span><span class="sxs-lookup"><span data-stu-id="01205-104">Methods</span></span>  
  
|<span data-ttu-id="01205-105">Метод</span><span class="sxs-lookup"><span data-stu-id="01205-105">Method</span></span>|<span data-ttu-id="01205-106">Описание</span><span class="sxs-lookup"><span data-stu-id="01205-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01205-107">Метод DefineGenericParam</span><span class="sxs-lookup"><span data-stu-id="01205-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="01205-108">Создает определение для параметра универсального типа и получает маркер для этого параметра универсального типа.</span><span class="sxs-lookup"><span data-stu-id="01205-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="01205-109">Метод DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="01205-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="01205-110">Создает универсальный экземпляр метода и получает маркер для определения.</span><span class="sxs-lookup"><span data-stu-id="01205-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="01205-111">Метод GetDeltaSaveSize</span><span class="sxs-lookup"><span data-stu-id="01205-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="01205-112">Возвращает значение, указывающее разницу в размере данных, необходимых для выражения изменений в текущем сеансе "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="01205-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="01205-113">Метод ResetENCLog</span><span class="sxs-lookup"><span data-stu-id="01205-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="01205-114">Сбрасывает журнал изменения и продолжения и запускает новый сеанс.</span><span class="sxs-lookup"><span data-stu-id="01205-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="01205-115">Метод SaveDelta</span><span class="sxs-lookup"><span data-stu-id="01205-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="01205-116">Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный файл.</span><span class="sxs-lookup"><span data-stu-id="01205-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="01205-117">Метод SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="01205-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="01205-118">Сохраняет изменения из текущего сеанса "изменить и продолжить" в память.</span><span class="sxs-lookup"><span data-stu-id="01205-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="01205-119">Метод SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="01205-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="01205-120">Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="01205-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="01205-121">Метод SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="01205-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="01205-122">Задает значения свойств для определения универсального параметра, на которое ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="01205-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01205-123">Требования</span><span class="sxs-lookup"><span data-stu-id="01205-123">Requirements</span></span>  
 <span data-ttu-id="01205-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01205-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01205-125">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="01205-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01205-126">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01205-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01205-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01205-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01205-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="01205-128">See also</span></span>

- [<span data-ttu-id="01205-129">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="01205-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="01205-130">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="01205-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
