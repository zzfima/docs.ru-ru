---
title: Интерфейс IMetaDataDispenserEx
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431147"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="e399f-102">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="e399f-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="e399f-103">Расширяет интерфейс [интерфейса IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) , чтобы предоставить возможность контролировать работу API метаданных в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e399f-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e399f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e399f-104">Methods</span></span>  
  
|<span data-ttu-id="e399f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e399f-105">Method</span></span>|<span data-ttu-id="e399f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e399f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e399f-107">Метод FindAssembly</span><span class="sxs-lookup"><span data-stu-id="e399f-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="e399f-108">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="e399f-108">This method is not implemented.</span></span> <span data-ttu-id="e399f-109">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e399f-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="e399f-110">Метод FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="e399f-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="e399f-111">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="e399f-111">This method is not implemented.</span></span> <span data-ttu-id="e399f-112">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e399f-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="e399f-113">Метод GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="e399f-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="e399f-114">Возвращает каталог, содержащий текущую среду CLR.</span><span class="sxs-lookup"><span data-stu-id="e399f-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="e399f-115">Этот метод поддерживается только для использования необработанными отладчиками.</span><span class="sxs-lookup"><span data-stu-id="e399f-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="e399f-116">Если вызывается из другого компонента, он возвратит E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e399f-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="e399f-117">Метод GetOption</span><span class="sxs-lookup"><span data-stu-id="e399f-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="e399f-118">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e399f-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="e399f-119">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e399f-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="e399f-120">Метод OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="e399f-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="e399f-121">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="e399f-121">This method is not implemented.</span></span> <span data-ttu-id="e399f-122">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e399f-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="e399f-123">Метод SetOption</span><span class="sxs-lookup"><span data-stu-id="e399f-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="e399f-124">Задает для указанного параметра заданное значение для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e399f-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="e399f-125">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="e399f-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e399f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="e399f-126">Requirements</span></span>  
 <span data-ttu-id="e399f-127">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e399f-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e399f-128">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e399f-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e399f-129">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e399f-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e399f-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e399f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e399f-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="e399f-131">See also</span></span>

- [<span data-ttu-id="e399f-132">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="e399f-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="e399f-133">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="e399f-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="e399f-134">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e399f-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e399f-135">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e399f-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
