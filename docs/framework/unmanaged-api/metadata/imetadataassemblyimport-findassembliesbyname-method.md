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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 454391eb7a5f1821438837c8fb7e5f8bad6b5723
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651663"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="ff81e-102">Метод IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="ff81e-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="ff81e-103">Возвращает массив сборок с указанным `szAssemblyName` параметр, с помощью стандартных правил, применяемых средой выполнения (CLR) для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="ff81e-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff81e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff81e-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff81e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff81e-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="ff81e-106">[in] Корневой каталог, в котором осуществляется поиск заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="ff81e-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="ff81e-107">Если это значение `null`, `FindAssembliesByName` будет искать только в глобальном кэше сборок для сборки.</span><span class="sxs-lookup"><span data-stu-id="ff81e-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="ff81e-108">[in] Список разделенных точкой с запятой подкаталоги (например, «bin; bin2»), в корневом каталоге, в котором следует искать сборки.</span><span class="sxs-lookup"><span data-stu-id="ff81e-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="ff81e-109">В дополнение к указанным в правилах проверки по умолчанию проверяются следующие каталоги.</span><span class="sxs-lookup"><span data-stu-id="ff81e-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ff81e-110">[in] Имя сборки для поиска.</span><span class="sxs-lookup"><span data-stu-id="ff81e-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="ff81e-111">Формат этой строки определяется в классе справочной странице для <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="ff81e-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="ff81e-112">[in] Массив объектов типа [IUnknown](/cpp/atl/iunknown) для размещения `IMetadataAssemblyImport` указателей на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ff81e-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ff81e-113">[out] Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="ff81e-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="ff81e-114">[out] Число возвращаемых указателя на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ff81e-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="ff81e-115">То есть число указателей интерфейса непосредственно в `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="ff81e-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff81e-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff81e-116">Return Value</span></span>  
  
|<span data-ttu-id="ff81e-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff81e-117">HRESULT</span></span>|<span data-ttu-id="ff81e-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="ff81e-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ff81e-119">`FindAssembliesByName` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ff81e-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ff81e-120">Не будут присутствовать сборки.</span><span class="sxs-lookup"><span data-stu-id="ff81e-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff81e-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff81e-121">Remarks</span></span>  
 <span data-ttu-id="ff81e-122">Имя сборки, `FindAssembliesByName` метод находит сборку, выполнив следующие стандартные правила для разрешения ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="ff81e-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="ff81e-123">(Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настроить различные аспекты контекста распознавателя, такие как путь поиска базового и частных приложений.</span><span class="sxs-lookup"><span data-stu-id="ff81e-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="ff81e-124">`FindAssembliesByName` Методу требуется быть инициализирована в процессе для вызова логики разрешения сборки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ff81e-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="ff81e-125">Таким образом, необходимо вызвать [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (передавая COINITEE_DEFAULT) перед вызовом `FindAssembliesByName`и выполните с помощью вызова [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="ff81e-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="ff81e-126">`FindAssembliesByName` Возвращает [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) указатель файла, содержащего манифест сборки для имени сборки, передаваемой в.</span><span class="sxs-lookup"><span data-stu-id="ff81e-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="ff81e-127">Если указанное имя сборки (например, если он не включает версию) задан не полностью, может быть возвращено несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="ff81e-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="ff81e-128">`FindAssembliesByName` обычно используется с помощью компилятора, который пытается найти сборку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="ff81e-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff81e-129">Требования</span><span class="sxs-lookup"><span data-stu-id="ff81e-129">Requirements</span></span>  
 <span data-ttu-id="ff81e-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff81e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff81e-131">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff81e-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff81e-132">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff81e-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff81e-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff81e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff81e-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ff81e-134">See also</span></span>
- [<span data-ttu-id="ff81e-135">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ff81e-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ff81e-136">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="ff81e-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
