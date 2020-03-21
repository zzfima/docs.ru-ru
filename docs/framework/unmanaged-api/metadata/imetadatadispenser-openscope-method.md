---
title: Метод IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175945"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="c89d4-102">Метод IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="c89d4-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="c89d4-103">Открывает существующий файл на диске и отображает свои метаданные в память.</span><span class="sxs-lookup"><span data-stu-id="c89d4-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c89d4-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c89d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c89d4-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="c89d4-106">(в) Имя файла, которое будет открыто.</span><span class="sxs-lookup"><span data-stu-id="c89d4-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="c89d4-107">Файл должен содержать метаданные общего времени выполнения языка (CLR).</span><span class="sxs-lookup"><span data-stu-id="c89d4-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="c89d4-108">(в) Значение значения [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления указать режим (читать, писать и так далее) для открытия.</span><span class="sxs-lookup"><span data-stu-id="c89d4-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="c89d4-109">(в) IID желаемого интерфейса метаданных, который должен быть возвращен; абонент будет использовать интерфейс для импорта (чтения) или испускателя (записи) метаданных.</span><span class="sxs-lookup"><span data-stu-id="c89d4-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="c89d4-110">Значение `riid` должно указывать один из интерфейсов "импорт" или "излучать".</span><span class="sxs-lookup"><span data-stu-id="c89d4-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="c89d4-111">Действительные значения— IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="c89d4-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="c89d4-112">(ваут) Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="c89d4-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c89d4-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="c89d4-113">Remarks</span></span>  
 <span data-ttu-id="c89d4-114">Копия метаданных в памяти может быть запрошена с помощью методов одного из «импортных» интерфейсов или добавлена к методам одного из интерфейсов «излучать».</span><span class="sxs-lookup"><span data-stu-id="c89d4-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="c89d4-115">Если целевой файл не содержит метаданных `OpenScope` CLR, метод выйдет из строя.</span><span class="sxs-lookup"><span data-stu-id="c89d4-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="c89d4-116">В версии .NET Framework 1.0 и версии 1.1, если область открыта с `dwOpenFlags` набором к read, она имеет право на обмен.</span><span class="sxs-lookup"><span data-stu-id="c89d4-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="c89d4-117">То есть, если `OpenScope` последующие вызовы передаются во имя файла, который был ранее открыт, существующая область используется повторно и не создается новый набор структур данных.</span><span class="sxs-lookup"><span data-stu-id="c89d4-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="c89d4-118">Тем не менее, проблемы могут возникнуть из-за этого обмена.</span><span class="sxs-lookup"><span data-stu-id="c89d4-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="c89d4-119">В версии .NET Framework 2.0 `dwOpenFlags` области области, открытые с набором ofRead, больше не являются общими.</span><span class="sxs-lookup"><span data-stu-id="c89d4-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="c89d4-120">Используйте значение ReadOnly, чтобы можно было поделиться областью.</span><span class="sxs-lookup"><span data-stu-id="c89d4-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="c89d4-121">При совместном использовании области запросы, в которых используются интерфейсы метаданных "читать/писать", завершаются неудачей.</span><span class="sxs-lookup"><span data-stu-id="c89d4-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c89d4-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c89d4-122">Requirements</span></span>  
 <span data-ttu-id="c89d4-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c89d4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c89d4-124">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c89d4-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c89d4-125">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c89d4-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c89d4-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89d4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89d4-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c89d4-127">See also</span></span>

- [<span data-ttu-id="c89d4-128">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c89d4-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="c89d4-129">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c89d4-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c89d4-130">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c89d4-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c89d4-131">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="c89d4-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="c89d4-132">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c89d4-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c89d4-133">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c89d4-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c89d4-134">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c89d4-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c89d4-135">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c89d4-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
