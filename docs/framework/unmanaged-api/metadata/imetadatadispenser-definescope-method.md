---
title: "Метод IMetaDataDispenser::DefineScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser.DefineScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 964e6df1b6aba7ca85b627cf19c38f5df600b6ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="f6887-102">Метод IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="f6887-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="f6887-103">Создает новую область в памяти, в котором можно создать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="f6887-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6887-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6887-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6887-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6887-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="f6887-106">[in] Код CLSID версии структуры метаданных должен быть создан.</span><span class="sxs-lookup"><span data-stu-id="f6887-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="f6887-107">Это значение должно быть CLSID_CorMetaDataRuntime для платформы .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="f6887-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="f6887-108">[in] Флаги, определяющие параметры.</span><span class="sxs-lookup"><span data-stu-id="f6887-108">[in] Flags that specify options.</span></span> <span data-ttu-id="f6887-109">Это значение должно быть нулем для .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="f6887-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="f6887-110">[in] Идентификатор IID интерфейса новых метаданных должен быть возвращен; вызывающий объект будет использовать интерфейс для создания новых метаданных.</span><span class="sxs-lookup"><span data-stu-id="f6887-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="f6887-111">Значение `riid` необходимо указать один из интерфейсов «выдачи».</span><span class="sxs-lookup"><span data-stu-id="f6887-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="f6887-112">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="f6887-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="f6887-113">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f6887-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6887-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6887-114">Remarks</span></span>  
 <span data-ttu-id="f6887-115">`DefineScope`Создает набор таблиц метаданных в памяти, уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице модуля для блоком компиляции.</span><span class="sxs-lookup"><span data-stu-id="f6887-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="f6887-116">Можно добавить атрибуты область метаданных в целом с помощью [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) метод соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="f6887-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6887-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f6887-117">Requirements</span></span>  
 <span data-ttu-id="f6887-118">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6887-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6887-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6887-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6887-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6887-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6887-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6887-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6887-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f6887-122">See Also</span></span>  
 [<span data-ttu-id="f6887-123">IMetaDataDispenser-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f6887-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="f6887-124">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f6887-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="f6887-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="f6887-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="f6887-126">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="f6887-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f6887-127">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f6887-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
