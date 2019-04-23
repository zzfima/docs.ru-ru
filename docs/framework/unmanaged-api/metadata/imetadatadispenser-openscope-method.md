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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b94987631f7dbbe39e585a8ea2c2252b9427613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079608"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="090b0-102">Метод IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="090b0-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="090b0-103">Открывает существующий файл на диске и сопоставляет его метаданные в память.</span><span class="sxs-lookup"><span data-stu-id="090b0-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="090b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="090b0-104">Syntax</span></span>  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="090b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="090b0-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="090b0-106">[in] Имя файла для открытия.</span><span class="sxs-lookup"><span data-stu-id="090b0-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="090b0-107">Файл должен содержать метаданных (CLR) среды CLR.</span><span class="sxs-lookup"><span data-stu-id="090b0-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="090b0-108">[in] Значение [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисление для задания режима (чтение, запись и так далее) для открытия.</span><span class="sxs-lookup"><span data-stu-id="090b0-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="090b0-109">[in] IID интерфейса новых метаданных должна быть возвращена. вызывающий объект будет использовать интерфейс для импорта (чтение) или выдачи метаданных (запись).</span><span class="sxs-lookup"><span data-stu-id="090b0-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="090b0-110">Значение `riid` необходимо указать один из интерфейсов «import» или «выдает».</span><span class="sxs-lookup"><span data-stu-id="090b0-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="090b0-111">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="090b0-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="090b0-112">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="090b0-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="090b0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="090b0-113">Remarks</span></span>  
 <span data-ttu-id="090b0-114">Копия в памяти метаданных можно запрашивать с помощью методов одного из интерфейсов «импорт», или добавить в методы одного из интерфейсов «выдает».</span><span class="sxs-lookup"><span data-stu-id="090b0-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="090b0-115">Если целевой файл не содержит метаданные среды CLR, `OpenScope` метод завершится с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="090b0-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="090b0-116">В .NET Framework версии 1.0 и 1.1, если область открывается с `dwOpenFlags` значение ofRead, он подходит для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="090b0-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="090b0-117">То есть если последующие вызовы `OpenScope` передайте имя файла, который ранее был открыт повторно существующую область и не создается новый набор структур данных.</span><span class="sxs-lookup"><span data-stu-id="090b0-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="090b0-118">Тем не менее могут возникнуть проблемы из-за этого совместного использования.</span><span class="sxs-lookup"><span data-stu-id="090b0-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="090b0-119">В платформе .NET Framework версии 2.0 области открывается с `dwOpenFlags` равным ofRead больше не являются общими.</span><span class="sxs-lookup"><span data-stu-id="090b0-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="090b0-120">Используйте значение ofReadOnly разрешающее область для совместного использования.</span><span class="sxs-lookup"><span data-stu-id="090b0-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="090b0-121">При совместном использовании области запросы, использующие «чтение/запись» интерфейсы метаданных завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="090b0-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="090b0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="090b0-122">Requirements</span></span>  
 <span data-ttu-id="090b0-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="090b0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="090b0-124">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="090b0-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="090b0-125">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="090b0-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="090b0-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="090b0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="090b0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="090b0-127">See also</span></span>

- [<span data-ttu-id="090b0-128">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="090b0-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="090b0-129">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="090b0-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="090b0-130">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="090b0-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="090b0-131">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="090b0-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="090b0-132">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="090b0-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="090b0-133">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="090b0-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="090b0-134">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="090b0-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="090b0-135">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="090b0-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
