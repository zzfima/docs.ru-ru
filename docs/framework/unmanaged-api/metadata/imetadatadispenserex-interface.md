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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d930088d6e621885d14fc4bdab2475aa27594e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448704"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="c0bd8-102">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c0bd8-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="c0bd8-103">Расширяет [IMetaDataDispenser-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) интерфейс, чтобы иметь возможность контролировать работу интерфейсов API метаданных в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0bd8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c0bd8-104">Methods</span></span>  
  
|<span data-ttu-id="c0bd8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c0bd8-105">Method</span></span>|<span data-ttu-id="c0bd8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c0bd8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0bd8-107">Метод FindAssembly</span><span class="sxs-lookup"><span data-stu-id="c0bd8-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="c0bd8-108">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-108">This method is not implemented.</span></span> <span data-ttu-id="c0bd8-109">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="c0bd8-110">Метод FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="c0bd8-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="c0bd8-111">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-111">This method is not implemented.</span></span> <span data-ttu-id="c0bd8-112">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="c0bd8-113">Метод GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="c0bd8-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="c0bd8-114">Возвращает каталог, содержащий текущий общеязыковая среда выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="c0bd8-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="c0bd8-115">Этот метод поддерживается только для использования в отладчиках out of process.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="c0bd8-116">Если вызывается из другого компонента, возвращается значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="c0bd8-117">Метод GetOption</span><span class="sxs-lookup"><span data-stu-id="c0bd8-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="c0bd8-118">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="c0bd8-119">Параметр определяет способ обработки вызовов текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="c0bd8-120">Метод OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="c0bd8-121">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-121">This method is not implemented.</span></span> <span data-ttu-id="c0bd8-122">При вызове возвращает значение E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="c0bd8-123">Метод SetOption</span><span class="sxs-lookup"><span data-stu-id="c0bd8-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="c0bd8-124">Устанавливает для указанного параметра заданное значение для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="c0bd8-125">Параметр определяет способ обработки вызовов текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0bd8-126">Требования</span><span class="sxs-lookup"><span data-stu-id="c0bd8-126">Requirements</span></span>  
 <span data-ttu-id="c0bd8-127">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0bd8-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0bd8-128">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0bd8-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0bd8-129">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0bd8-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0bd8-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0bd8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bd8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c0bd8-131">See Also</span></span>  
 [<span data-ttu-id="c0bd8-132">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="c0bd8-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="c0bd8-133">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c0bd8-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="c0bd8-134">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c0bd8-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c0bd8-135">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c0bd8-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
