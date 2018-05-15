---
title: Метод IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 562b6fcd015441ce5eb6b5f0ab7a4f361bb229c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="c1954-102">Метод IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="c1954-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="c1954-103">Возвращает область памяти сопоставленных файлов и тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c1954-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1954-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1954-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1954-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1954-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="c1954-106">[out] Указатель на начало сопоставленный файл.</span><span class="sxs-lookup"><span data-stu-id="c1954-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="c1954-107">[out] Размер сопоставленной области.</span><span class="sxs-lookup"><span data-stu-id="c1954-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="c1954-108">Если `pdwMappingType` — `fmFlat`, размер файла.</span><span class="sxs-lookup"><span data-stu-id="c1954-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="c1954-109">[out] Объект [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) значение, указывающее тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="c1954-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="c1954-110">Текущая реализация среды common language runtime (CLR) всегда возвращает `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="c1954-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="c1954-111">Другие значения зарезервированы для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="c1954-111">Other values are reserved for future use.</span></span> <span data-ttu-id="c1954-112">Тем не менее следует всегда проверять возвращаемое значение, поскольку другие значения могут быть включены в будущих версиях или в наборах исправлений.</span><span class="sxs-lookup"><span data-stu-id="c1954-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1954-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c1954-113">Return Value</span></span>  
  
|<span data-ttu-id="c1954-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1954-114">HRESULT</span></span>|<span data-ttu-id="c1954-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c1954-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c1954-116">Все выходные данные заполняются.</span><span class="sxs-lookup"><span data-stu-id="c1954-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="c1954-117">NULL был передан в качестве значения аргумента.</span><span class="sxs-lookup"><span data-stu-id="c1954-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="c1954-118">В реализации CLR не может предоставить сведения об области памяти.</span><span class="sxs-lookup"><span data-stu-id="c1954-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="c1954-119">Это может происходить по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="c1954-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="c1954-120">-Области метаданных была открыта с `ofWrite` или `ofCopyMemory` флаг.</span><span class="sxs-lookup"><span data-stu-id="c1954-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="c1954-121">-Области метаданных был открыт без `ofReadOnly` флаг.</span><span class="sxs-lookup"><span data-stu-id="c1954-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="c1954-122">- [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метода, использовавшегося для открытия только метаданные части файла.</span><span class="sxs-lookup"><span data-stu-id="c1954-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="c1954-123">-Файл не является файлом переносимого исполняемого (PE).</span><span class="sxs-lookup"><span data-stu-id="c1954-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="c1954-124">**Примечание:** эти условия зависят от реализации CLR, а скорее всего, будут ослабляется в будущих версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c1954-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1954-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1954-125">Remarks</span></span>  
 <span data-ttu-id="c1954-126">Объем памяти, `ppvData` указывает допустим только при условии, что открыт базовой области метаданных.</span><span class="sxs-lookup"><span data-stu-id="c1954-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="c1954-127">В этот метод для работы, при сопоставлении метаданных из файла на диске в память, вызвав [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) метод, необходимо указать `ofReadOnly` флаг, а также не указать `ofWrite` или `ofCopyMemory` флаг.</span><span class="sxs-lookup"><span data-stu-id="c1954-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="c1954-128">Выбор типа сопоставления файлов для каждой области относится к заданной реализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="c1954-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="c1954-129">Его нельзя установить для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c1954-129">It cannot be set by the user.</span></span> <span data-ttu-id="c1954-130">Текущая реализация среды CLR всегда возвращает `fmFlat` в `pdwMappingType`, но это может измениться в будущих версиях среды CLR или в будущих выпусках данной версии службы.</span><span class="sxs-lookup"><span data-stu-id="c1954-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="c1954-131">Всегда следует проверять возвращаемое значение `pdwMappingType`, так как различные типы будут иметь разные макеты и смещения.</span><span class="sxs-lookup"><span data-stu-id="c1954-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="c1954-132">Передача значения NULL для любого из трех параметров не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c1954-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="c1954-133">Метод возвращает `E_INVALIDARG`, и ни один из выходов заполняются.</span><span class="sxs-lookup"><span data-stu-id="c1954-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="c1954-134">Игнорирование типа сопоставления или размер области может вызвать аварийное завершение программы.</span><span class="sxs-lookup"><span data-stu-id="c1954-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1954-135">Требования</span><span class="sxs-lookup"><span data-stu-id="c1954-135">Requirements</span></span>  
 <span data-ttu-id="c1954-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1954-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1954-137">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1954-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1954-138">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1954-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1954-139">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1954-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1954-140">См. также</span><span class="sxs-lookup"><span data-stu-id="c1954-140">See Also</span></span>  
 [<span data-ttu-id="c1954-141">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="c1954-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="c1954-142">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="c1954-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
