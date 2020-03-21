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
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177642"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="43d44-102">Метод IMetaDataDispenser::DefineScope</span><span class="sxs-lookup"><span data-stu-id="43d44-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="43d44-103">Создает новую область памяти, в которой можно создавать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="43d44-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43d44-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43d44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43d44-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="43d44-106">(в) CLSID версии структур метаданных, которые будут созданы.</span><span class="sxs-lookup"><span data-stu-id="43d44-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="43d44-107">Это значение должно быть CLSID_CorMetaDataRuntime для версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="43d44-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="43d44-108">(в) Флаги, определяющие параметры.</span><span class="sxs-lookup"><span data-stu-id="43d44-108">[in] Flags that specify options.</span></span> <span data-ttu-id="43d44-109">Это значение должно быть нулевым для рамочной 2.0 .NET.</span><span class="sxs-lookup"><span data-stu-id="43d44-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="43d44-110">(в) IID желаемого интерфейса метаданных, который должен быть возвращен; абонент будет использовать интерфейс для создания новых метаданных.</span><span class="sxs-lookup"><span data-stu-id="43d44-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="43d44-111">Значение `riid` должно указывать один из интерфейсов "emit".</span><span class="sxs-lookup"><span data-stu-id="43d44-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="43d44-112">Допустимые значения — это IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="43d44-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="43d44-113">(ваут) Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="43d44-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43d44-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="43d44-114">Remarks</span></span>  
 <span data-ttu-id="43d44-115">`DefineScope`создает набор таблиц метаданных в памяти, генерирует уникальный GUID (идентификатор версии модуля, или MVID) для метаданных и создает запись в таблице модуля для испускаемого единицы компиляции.</span><span class="sxs-lookup"><span data-stu-id="43d44-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="43d44-116">Приложить атрибуты к области метаданных в целом можно с помощью метода [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="43d44-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43d44-117">Требования</span><span class="sxs-lookup"><span data-stu-id="43d44-117">Requirements</span></span>  
 <span data-ttu-id="43d44-118">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43d44-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43d44-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43d44-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43d44-120">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43d44-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43d44-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43d44-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d44-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43d44-122">See also</span></span>

- [<span data-ttu-id="43d44-123">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="43d44-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="43d44-124">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="43d44-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="43d44-125">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="43d44-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="43d44-126">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="43d44-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="43d44-127">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="43d44-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
