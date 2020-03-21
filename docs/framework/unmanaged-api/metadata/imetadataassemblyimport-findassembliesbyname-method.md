---
title: Метод IMetaDataAssemblyImport::FindAssembliesByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177803"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="327f8-102">Метод IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="327f8-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="327f8-103">Получает массив сборок с указанным `szAssemblyName` параметром, используя стандартные правила, используемые общим временем выполнения языка (CLR) для решения ссылок.</span><span class="sxs-lookup"><span data-stu-id="327f8-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="327f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="327f8-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="327f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="327f8-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="327f8-106">(в) Корневой каталог, в котором можно найти данную сборку.</span><span class="sxs-lookup"><span data-stu-id="327f8-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="327f8-107">Если это значение `null`настроено на, `FindAssembliesByName` будет выглядеть только в глобальном кэше сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="327f8-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="327f8-108">(в) Список субдиректоров, делемых заполколонией (например, "bin;bin2"), в котором можно найти сборку.</span><span class="sxs-lookup"><span data-stu-id="327f8-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="327f8-109">Эти каталоги проверяются в дополнение к тем, которые указаны в правилах зондирования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="327f8-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="327f8-110">(в) Название сборки, чтобы найти.</span><span class="sxs-lookup"><span data-stu-id="327f8-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="327f8-111">Формат этой строки определяется на странице <xref:System.Reflection.AssemblyName>ссылки класса для .</span><span class="sxs-lookup"><span data-stu-id="327f8-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="327f8-112">(в) Массив типа [IUnknown,](/cpp/atl/iunknown) в котором `IMetadataAssemblyImport` можно поставить указатели интерфейса.</span><span class="sxs-lookup"><span data-stu-id="327f8-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="327f8-113">(ваут) Максимальное количество указателей интерфейса, `ppIUnk`которые могут быть размещены в .</span><span class="sxs-lookup"><span data-stu-id="327f8-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="327f8-114">(ваут) Число указателей интерфейса вернулось.</span><span class="sxs-lookup"><span data-stu-id="327f8-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="327f8-115">То есть, количество указателей интерфейса `ppIUnk`фактически помещено в .</span><span class="sxs-lookup"><span data-stu-id="327f8-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="327f8-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="327f8-116">Return Value</span></span>  
  
|<span data-ttu-id="327f8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="327f8-117">HRESULT</span></span>|<span data-ttu-id="327f8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="327f8-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="327f8-119">`FindAssembliesByName`вернулся успешно.</span><span class="sxs-lookup"><span data-stu-id="327f8-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="327f8-120">Сборок нет.</span><span class="sxs-lookup"><span data-stu-id="327f8-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="327f8-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="327f8-121">Remarks</span></span>  
 <span data-ttu-id="327f8-122">Учитывая имя сборки, `FindAssembliesByName` метод находит сборку, следуя стандартным правилам для разрешения ссылок сборки.</span><span class="sxs-lookup"><span data-stu-id="327f8-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="327f8-123">(Для получения дополнительной информации, [см. Как Runtime находит сборки](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему настроить различные аспекты контекста разрешения сборки, такие как база приложений и частный путь поиска.</span><span class="sxs-lookup"><span data-stu-id="327f8-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="327f8-124">Метод `FindAssembliesByName` требует, чтобы CLR был инициализирован в процессе, чтобы вызвать логику разрешения сборки.</span><span class="sxs-lookup"><span data-stu-id="327f8-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="327f8-125">Таким образом, вы должны позвонить [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (проходя COINITEE_DEFAULT) перед вызовом, `FindAssembliesByName`а затем следовать с вызовом [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="327f8-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="327f8-126">`FindAssembliesByName`возвращает указатель [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) в файл, содержащий манифест сборки для имени сборки, в котором находится передаваемое.</span><span class="sxs-lookup"><span data-stu-id="327f8-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="327f8-127">Если данное имя сборки не полностью указано (например, если оно не содержит версию), может быть возвращено несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="327f8-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="327f8-128">`FindAssembliesByName`обычно используется компилятором, который пытается найти ссылку сборки во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="327f8-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="327f8-129">Требования</span><span class="sxs-lookup"><span data-stu-id="327f8-129">Requirements</span></span>  
 <span data-ttu-id="327f8-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="327f8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="327f8-131">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="327f8-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="327f8-132">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="327f8-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="327f8-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="327f8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="327f8-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="327f8-134">See also</span></span>

- [<span data-ttu-id="327f8-135">Как Время выполнения находит сборки</span><span class="sxs-lookup"><span data-stu-id="327f8-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="327f8-136">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="327f8-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
