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
ms.openlocfilehash: 04e0fabfc0d70c9d922e0715f32bd07237ce8741
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442308"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="b4d7f-102">Метод IMetaDataDispenser::OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="b4d7f-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="b4d7f-103">Открывает область памяти, которая содержит существующие метаданные.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="b4d7f-104">Это значит, что этот метод открывает указанную область памяти, в которой существующие данные обрабатываются как метаданные.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d7f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4d7f-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4d7f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4d7f-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="b4d7f-107">окне Указатель, указывающий начальный адрес области памяти.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="b4d7f-108">окне Размер области памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="b4d7f-109">окне Значение перечисления [коропенфлагс](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) , определяющее режим (чтение, запись и т. д.) для открытия.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="b4d7f-110">окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтения) или выдачи (записи) метаданных.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="b4d7f-111">Значение `riid` должно указывать один из интерфейсов "import" или "Emit".</span><span class="sxs-lookup"><span data-stu-id="b4d7f-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="b4d7f-112">Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="b4d7f-113">заполняет Указатель на возвращаемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4d7f-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="b4d7f-114">Remarks</span></span>  
 <span data-ttu-id="b4d7f-115">Копию метаданных в памяти можно запросить с помощью методов из одного из интерфейсов "Импорт" или добавить к методам из одного из интерфейсов "выдачи".</span><span class="sxs-lookup"><span data-stu-id="b4d7f-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="b4d7f-116">Метод `OpenScopeOnMemory` аналогичен методу [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) , за исключением того, что интересующие метаданные уже существуют в памяти, а не в файле на диске.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="b4d7f-117">Если целевая область памяти не содержит метаданных среды CLR, метод `OpenScopeOnMemory` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b4d7f-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d7f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="b4d7f-118">Requirements</span></span>  
 <span data-ttu-id="b4d7f-119">**Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d7f-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d7f-120">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b4d7f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4d7f-121">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4d7f-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4d7f-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d7f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d7f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b4d7f-123">See also</span></span>

- [<span data-ttu-id="b4d7f-124">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="b4d7f-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="b4d7f-125">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="b4d7f-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="b4d7f-126">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="b4d7f-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="b4d7f-127">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="b4d7f-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="b4d7f-128">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b4d7f-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b4d7f-129">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b4d7f-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="b4d7f-130">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b4d7f-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4d7f-131">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b4d7f-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
