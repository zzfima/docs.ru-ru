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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175269"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="2a83b-102">Метод IMetaDataInfo::GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="2a83b-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="2a83b-103">Получает область памяти отображенный файл и тип отображения.</span><span class="sxs-lookup"><span data-stu-id="2a83b-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a83b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a83b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a83b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2a83b-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="2a83b-106">(ваут) Указатель на начало отображаемого файла.</span><span class="sxs-lookup"><span data-stu-id="2a83b-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="2a83b-107">(ваут) Размер отображенный регион.</span><span class="sxs-lookup"><span data-stu-id="2a83b-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="2a83b-108">Если `pdwMappingType` `fmFlat`это так, то это размер файла.</span><span class="sxs-lookup"><span data-stu-id="2a83b-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="2a83b-109">(ваут) Значение [CorFileMapping,](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) которое указывает тип отображения.</span><span class="sxs-lookup"><span data-stu-id="2a83b-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="2a83b-110">Текущая реализация общего времени выполнения языка (CLR) всегда возвращается. `fmFlat`</span><span class="sxs-lookup"><span data-stu-id="2a83b-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="2a83b-111">Другие значения зарезервированы для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="2a83b-111">Other values are reserved for future use.</span></span> <span data-ttu-id="2a83b-112">Однако всегда следует проверять возвращенное значение, поскольку другие значения могут быть включены в будущих версиях или выпусках служб.</span><span class="sxs-lookup"><span data-stu-id="2a83b-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a83b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2a83b-113">Return Value</span></span>  
  
|<span data-ttu-id="2a83b-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a83b-114">HRESULT</span></span>|<span data-ttu-id="2a83b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="2a83b-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2a83b-116">Все выходы заполнены.</span><span class="sxs-lookup"><span data-stu-id="2a83b-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="2a83b-117">NULL был принят в качестве аргумента значение.</span><span class="sxs-lookup"><span data-stu-id="2a83b-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="2a83b-118">Реализация CLR не может предоставить информацию о области памяти.</span><span class="sxs-lookup"><span data-stu-id="2a83b-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="2a83b-119">Это может происходить по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="2a83b-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="2a83b-120">- Область метаданных была `ofWrite` открыта `ofCopyMemory` с флагом или флагом.</span><span class="sxs-lookup"><span data-stu-id="2a83b-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="2a83b-121">- Область метаданных была `ofReadOnly` открыта без флага.</span><span class="sxs-lookup"><span data-stu-id="2a83b-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="2a83b-122">- [Метод IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части метаданных файла.</span><span class="sxs-lookup"><span data-stu-id="2a83b-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="2a83b-123">- Файл не является портативным исполняемым (PE) файлом.</span><span class="sxs-lookup"><span data-stu-id="2a83b-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="2a83b-124">**Примечание:**  Эти условия зависят от реализации CLR и, вероятно, будут ослаблены в будущих версиях CLR.</span><span class="sxs-lookup"><span data-stu-id="2a83b-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a83b-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="2a83b-125">Remarks</span></span>  
 <span data-ttu-id="2a83b-126">Память, `ppvData` на которую указывает, действительна только до тех пор, пока открыта базовая область метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a83b-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="2a83b-127">Для того, чтобы этот метод работал, при составлении карты метаданных дискового файла в память, позвонив `ofReadOnly` в [метод IMetaDataDispenser::OpenScope,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) необходимо указать флаг, и вы не должны указывать флаг `ofWrite` или `ofCopyMemory` флаг.</span><span class="sxs-lookup"><span data-stu-id="2a83b-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="2a83b-128">Выбор типа картирования файлов для каждой области специфичен для данной реализации CLR.</span><span class="sxs-lookup"><span data-stu-id="2a83b-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="2a83b-129">Он не может быть установлен пользователем.</span><span class="sxs-lookup"><span data-stu-id="2a83b-129">It cannot be set by the user.</span></span> <span data-ttu-id="2a83b-130">Текущая реализация CLR всегда `fmFlat` `pdwMappingType`возвращается в , но это может измениться в будущих версиях CLR или в будущих релизах службы данной версии.</span><span class="sxs-lookup"><span data-stu-id="2a83b-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="2a83b-131">Вы всегда должны проверить `pdwMappingType`возвращенное значение в, потому что различные типы будут иметь различные макеты и смещения.</span><span class="sxs-lookup"><span data-stu-id="2a83b-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="2a83b-132">Прохождение NULL по любому из трех параметров не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="2a83b-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="2a83b-133">Метод возвращается, `E_INVALIDARG`и ни один из выходов не заполнен.</span><span class="sxs-lookup"><span data-stu-id="2a83b-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="2a83b-134">Игнорирование типа отображения или размера региона может привести к ненормальному прекращению программы.</span><span class="sxs-lookup"><span data-stu-id="2a83b-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a83b-135">Требования</span><span class="sxs-lookup"><span data-stu-id="2a83b-135">Requirements</span></span>  
 <span data-ttu-id="2a83b-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a83b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a83b-137">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a83b-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a83b-138">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a83b-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a83b-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a83b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a83b-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a83b-140">See also</span></span>

- [<span data-ttu-id="2a83b-141">Интерфейс IMetaDataInfo</span><span class="sxs-lookup"><span data-stu-id="2a83b-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="2a83b-142">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="2a83b-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
