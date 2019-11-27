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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436172"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="2d95e-102">Метод IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="2d95e-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="2d95e-103">Возвращает область памяти сопоставленного файла и тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2d95e-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d95e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d95e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d95e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d95e-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="2d95e-106">заполняет Указатель на начало сопоставленного файла.</span><span class="sxs-lookup"><span data-stu-id="2d95e-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="2d95e-107">заполняет Размер сопоставленной области.</span><span class="sxs-lookup"><span data-stu-id="2d95e-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="2d95e-108">Если `pdwMappingType` `fmFlat`, то это размер файла.</span><span class="sxs-lookup"><span data-stu-id="2d95e-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="2d95e-109">заполняет Значение [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) , указывающее тип сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2d95e-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="2d95e-110">Текущая реализация среды CLR всегда возвращает `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="2d95e-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="2d95e-111">Другие значения зарезервированы для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="2d95e-111">Other values are reserved for future use.</span></span> <span data-ttu-id="2d95e-112">Однако всегда следует проверять возвращаемое значение, так как в будущих версиях или выпусках служб могут быть включены другие значения.</span><span class="sxs-lookup"><span data-stu-id="2d95e-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d95e-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d95e-113">Return Value</span></span>  
  
|<span data-ttu-id="2d95e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d95e-114">HRESULT</span></span>|<span data-ttu-id="2d95e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2d95e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2d95e-116">Все выходные данные заполнены.</span><span class="sxs-lookup"><span data-stu-id="2d95e-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="2d95e-117">Значение NULL передано в качестве значения аргумента.</span><span class="sxs-lookup"><span data-stu-id="2d95e-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="2d95e-118">Реализация CLR не может предоставить сведения о области памяти.</span><span class="sxs-lookup"><span data-stu-id="2d95e-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="2d95e-119">Это может происходить по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="2d95e-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="2d95e-120">— Область метаданных была открыта с флагом `ofWrite` или `ofCopyMemory`.</span><span class="sxs-lookup"><span data-stu-id="2d95e-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="2d95e-121">— Область метаданных была открыта без флага `ofReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="2d95e-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="2d95e-122">— Метод [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части файла с метаданными.</span><span class="sxs-lookup"><span data-stu-id="2d95e-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="2d95e-123">— Файл не является переносимым исполняемым файлом (PE).</span><span class="sxs-lookup"><span data-stu-id="2d95e-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="2d95e-124">**Примечание.**  Эти условия зависят от реализации CLR и, скорее всего, будут ослаблены в будущих версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2d95e-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d95e-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="2d95e-125">Remarks</span></span>  
 <span data-ttu-id="2d95e-126">Память, на которую `ppvData` указывает, действительна только при условии, что базовая область метаданных открыта.</span><span class="sxs-lookup"><span data-stu-id="2d95e-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="2d95e-127">Чтобы этот метод работал, при сопоставлении метаданных файла на диске с памятью путем вызова метода [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) необходимо указать флаг `ofReadOnly` и не указывать `ofWrite` или флаг `ofCopyMemory`.</span><span class="sxs-lookup"><span data-stu-id="2d95e-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="2d95e-128">Выбранный тип сопоставления файлов для каждой области зависит от конкретной реализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2d95e-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="2d95e-129">Он не может быть задан пользователем.</span><span class="sxs-lookup"><span data-stu-id="2d95e-129">It cannot be set by the user.</span></span> <span data-ttu-id="2d95e-130">Текущая реализация CLR всегда возвращает `fmFlat` в `pdwMappingType`, но это может измениться в будущих версиях CLR или в будущих выпусках данной версии службы.</span><span class="sxs-lookup"><span data-stu-id="2d95e-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="2d95e-131">Всегда следует проверять возвращаемое значение в `pdwMappingType`, поскольку разные типы будут иметь разные макеты и смещения.</span><span class="sxs-lookup"><span data-stu-id="2d95e-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="2d95e-132">Передача значения NULL для любого из трех параметров не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2d95e-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="2d95e-133">Метод возвращает `E_INVALIDARG`, и ни один из выходных данных не заполнен.</span><span class="sxs-lookup"><span data-stu-id="2d95e-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="2d95e-134">Пропуск типа сопоставления или размера региона может привести к аварийному завершению программы.</span><span class="sxs-lookup"><span data-stu-id="2d95e-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d95e-135">Требования</span><span class="sxs-lookup"><span data-stu-id="2d95e-135">Requirements</span></span>  
 <span data-ttu-id="2d95e-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d95e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d95e-137">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2d95e-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d95e-138">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d95e-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d95e-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d95e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d95e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2d95e-140">See also</span></span>

- [<span data-ttu-id="2d95e-141">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="2d95e-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="2d95e-142">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="2d95e-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
