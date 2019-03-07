---
title: Метод IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8df46a3c6beed26e885e7dc13f97a7c68d2abcdc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487984"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="3b4b8-102">Метод IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="3b4b8-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="3b4b8-103">Создает новую область в памяти, в котором можно создать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b4b8-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b4b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b4b8-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="3b4b8-106">[in] CLSID создаваемого версии структуры метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="3b4b8-107">Это значение должно быть CLSID_CorMetaDataRuntime для платформы .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="3b4b8-108">[in] Флаги, определяющие параметры.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-108">[in] Flags that specify options.</span></span> <span data-ttu-id="3b4b8-109">Это значение должно быть ноль для .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="3b4b8-110">[in] IID интерфейса новых метаданных должна быть возвращена. вызывающий объект будет использовать интерфейс для создания новых метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="3b4b8-111">Значение `riid` необходимо указать один из интерфейсов «выдает».</span><span class="sxs-lookup"><span data-stu-id="3b4b8-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="3b4b8-112">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="3b4b8-113">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b4b8-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b4b8-114">Remarks</span></span>  
 <span data-ttu-id="3b4b8-115">`DefineScope` Создает набор таблиц метаданных в памяти, уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице модуля для блоком компиляции.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="3b4b8-116">Можно присоединить атрибуты в область действия метаданных в целом, используя [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) метод соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="3b4b8-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b4b8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="3b4b8-117">Requirements</span></span>  
 <span data-ttu-id="3b4b8-118">**Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b4b8-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4b8-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b4b8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b4b8-120">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b4b8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b4b8-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4b8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4b8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3b4b8-122">See also</span></span>
- [<span data-ttu-id="3b4b8-123">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="3b4b8-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="3b4b8-124">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="3b4b8-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3b4b8-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="3b4b8-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="3b4b8-126">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3b4b8-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b4b8-127">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3b4b8-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
