---
title: Метод IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175932"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="d1ca3-102">Метод IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="d1ca3-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="d1ca3-103">Открывает область памяти, содержащую существующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="d1ca3-104">То есть этот метод открывает заданную область памяти, в которой существующие данные рассматриваются как метаданные.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ca3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1ca3-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1ca3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1ca3-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="d1ca3-107">(в) Указатель, обоужаемый начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d1ca3-108">(в) Размер области памяти, байтов.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d1ca3-109">(в) Значение значения [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления указать режим (читать, писать и так далее) для открытия.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="d1ca3-110">(в) IID желаемого интерфейса метаданных, который должен быть возвращен; абонент будет использовать интерфейс для импорта (чтения) или испускателя (записи) метаданных.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="d1ca3-111">Значение `riid` должно указывать один из интерфейсов "импорт" или "излучать".</span><span class="sxs-lookup"><span data-stu-id="d1ca3-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="d1ca3-112">Действительные значения— IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d1ca3-113">(ваут) Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1ca3-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="d1ca3-114">Remarks</span></span>  
 <span data-ttu-id="d1ca3-115">Копия метаданных в памяти может быть запрошена с помощью методов одного из «импортных» интерфейсов или добавлена к методам одного из интерфейсов «излучать».</span><span class="sxs-lookup"><span data-stu-id="d1ca3-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="d1ca3-116">Метод `OpenScopeOnMemory` аналогичен [методу IMetaDataDispenser::OpenScope,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) за исключением того, что метаданные, представляющие интерес, уже существуют в памяти, а не в файле на диске.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="d1ca3-117">Если целевая область памяти не содержит метаданных общего времени `OpenScopeOnMemory` выполнения языка (CLR), метод выйдет из строя.</span><span class="sxs-lookup"><span data-stu-id="d1ca3-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ca3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d1ca3-118">Requirements</span></span>  
 <span data-ttu-id="d1ca3-119">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ca3-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ca3-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d1ca3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1ca3-121">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1ca3-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1ca3-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ca3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ca3-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d1ca3-123">See also</span></span>

- [<span data-ttu-id="d1ca3-124">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="d1ca3-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="d1ca3-125">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="d1ca3-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="d1ca3-126">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="d1ca3-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="d1ca3-127">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="d1ca3-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="d1ca3-128">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d1ca3-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d1ca3-129">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d1ca3-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d1ca3-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d1ca3-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d1ca3-131">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d1ca3-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
