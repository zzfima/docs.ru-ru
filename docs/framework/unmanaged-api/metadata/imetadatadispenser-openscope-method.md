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
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442326"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="b43eb-102">Метод IMetaDataDispenser::OpenScope</span><span class="sxs-lookup"><span data-stu-id="b43eb-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="b43eb-103">Открывает существующий файл на диске и сопоставляет его метаданные с памятью.</span><span class="sxs-lookup"><span data-stu-id="b43eb-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b43eb-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b43eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b43eb-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="b43eb-106">окне Имя открываемого файла.</span><span class="sxs-lookup"><span data-stu-id="b43eb-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="b43eb-107">Файл должен содержать метаданные среды CLR.</span><span class="sxs-lookup"><span data-stu-id="b43eb-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="b43eb-108">окне Значение перечисления [коропенфлагс](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) , определяющее режим (чтение, запись и т. д.) для открытия.</span><span class="sxs-lookup"><span data-stu-id="b43eb-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="b43eb-109">окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтения) или выдачи (записи) метаданных.</span><span class="sxs-lookup"><span data-stu-id="b43eb-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="b43eb-110">Значение `riid` должно указывать один из интерфейсов "import" или "Emit".</span><span class="sxs-lookup"><span data-stu-id="b43eb-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="b43eb-111">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="b43eb-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="b43eb-112">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b43eb-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b43eb-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="b43eb-113">Remarks</span></span>  
 <span data-ttu-id="b43eb-114">Копию метаданных в памяти можно запросить с помощью методов из одного из интерфейсов "Импорт" или добавить к методам из одного из интерфейсов "выдачи".</span><span class="sxs-lookup"><span data-stu-id="b43eb-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="b43eb-115">Если целевой файл не содержит метаданные CLR, метод `OpenScope` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b43eb-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="b43eb-116">В .NET Framework версии 1,0 и 1,1, если область открыта с `dwOpenFlags` установлен в значение Офреад, она может предоставлять общий доступ.</span><span class="sxs-lookup"><span data-stu-id="b43eb-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="b43eb-117">То есть, если последующие вызовы `OpenScope` передают имя ранее открытого файла, существующая область используется повторно, а новый набор структур данных не создается.</span><span class="sxs-lookup"><span data-stu-id="b43eb-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="b43eb-118">Тем не менее проблемы могут возникать из-за этого общего доступа.</span><span class="sxs-lookup"><span data-stu-id="b43eb-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="b43eb-119">В .NET Framework версии 2,0 области, открытые с `dwOpenFlags` установленным в Офреад, больше не являются общими.</span><span class="sxs-lookup"><span data-stu-id="b43eb-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="b43eb-120">Используйте значение Офреадонли, чтобы разрешить общий доступ к области.</span><span class="sxs-lookup"><span data-stu-id="b43eb-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="b43eb-121">При совместном использовании области запросы, использующие интерфейсы метаданных для чтения и записи, завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b43eb-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b43eb-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b43eb-122">Requirements</span></span>  
 <span data-ttu-id="b43eb-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b43eb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b43eb-124">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b43eb-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b43eb-125">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b43eb-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b43eb-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b43eb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43eb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="b43eb-127">See also</span></span>

- [<span data-ttu-id="b43eb-128">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="b43eb-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="b43eb-129">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b43eb-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="b43eb-130">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b43eb-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="b43eb-131">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b43eb-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="b43eb-132">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b43eb-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b43eb-133">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b43eb-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="b43eb-134">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b43eb-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b43eb-135">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b43eb-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
