---
title: Метод IMetaDataDispenser::OpenScopeOnMemory
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 11
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d206863736387df04157ed752a6269b22a884b9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="faeda-102">Метод IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="faeda-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="faeda-103">Открывает область памяти, содержащую существующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="faeda-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="faeda-104">То есть этот метод открывает заданную область памяти, в которой существующие данные интерпретируются как метаданные.</span><span class="sxs-lookup"><span data-stu-id="faeda-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faeda-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="faeda-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="faeda-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="faeda-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="faeda-107">[in] Указатель, который задает начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="faeda-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="faeda-108">[in] Размер области памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="faeda-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="faeda-109">[in] Значение [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления для задания режима (чтение, запись и так далее) для открытия.</span><span class="sxs-lookup"><span data-stu-id="faeda-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="faeda-110">[in] Идентификатор IID интерфейса новых метаданных должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтение) или выдачи метаданных (запись).</span><span class="sxs-lookup"><span data-stu-id="faeda-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="faeda-111">Значение `riid` необходимо указать один из интерфейсов «import» или «выдачи».</span><span class="sxs-lookup"><span data-stu-id="faeda-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="faeda-112">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="faeda-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="faeda-113">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="faeda-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faeda-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="faeda-114">Remarks</span></span>  
 <span data-ttu-id="faeda-115">Копия в памяти метаданных можно запрашивать с помощью методов одного из интерфейсов «импорт», или добавить в методы одного из интерфейсов «выдачи».</span><span class="sxs-lookup"><span data-stu-id="faeda-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="faeda-116">`OpenScopeOnMemory` Аналогичен методу [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) метода, за исключением того, что метаданные, представляющие интерес уже существует в памяти, а не в файле на диске.</span><span class="sxs-lookup"><span data-stu-id="faeda-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="faeda-117">Если целевая область памяти, не содержит метаданных среды CLR (CLR), `OpenScopeOnMemory` метод завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="faeda-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faeda-118">Требования</span><span class="sxs-lookup"><span data-stu-id="faeda-118">Requirements</span></span>  
 <span data-ttu-id="faeda-119">**Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faeda-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faeda-120">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="faeda-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="faeda-121">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="faeda-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="faeda-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faeda-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faeda-123">См. также</span><span class="sxs-lookup"><span data-stu-id="faeda-123">See Also</span></span>  
 [<span data-ttu-id="faeda-124">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="faeda-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="faeda-125">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="faeda-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="faeda-126">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="faeda-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="faeda-127">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="faeda-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="faeda-128">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="faeda-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="faeda-129">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="faeda-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="faeda-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="faeda-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="faeda-131">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="faeda-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
