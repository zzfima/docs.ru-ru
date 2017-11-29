---
title: "Метод IMetaDataAssemblyImport::FindAssembliesByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindAssembliesByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3b957430e66e4381a9be33ceb687d7aecba53a4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="37a7f-102">Метод IMetaDataAssemblyImport::FindAssembliesByName</span><span class="sxs-lookup"><span data-stu-id="37a7f-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="37a7f-103">Возвращает массив сборок с заданным `szAssemblyName` параметр, с помощью стандартных правил, применяемых средой выполнения (CLR) для разрешения ссылок.</span><span class="sxs-lookup"><span data-stu-id="37a7f-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37a7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="37a7f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="37a7f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="37a7f-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="37a7f-106">[in] Корневой каталог, в котором выполняется поиск заданной сборки.</span><span class="sxs-lookup"><span data-stu-id="37a7f-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="37a7f-107">Если это значение равно `null`, `FindAssembliesByName` будет осуществлять поиск сборки только в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="37a7f-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="37a7f-108">[in] Список разделенных точкой с запятой каталогов (например, «bin; bin2»), в корневом каталоге, в котором выполняется поиск для сборки.</span><span class="sxs-lookup"><span data-stu-id="37a7f-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="37a7f-109">Эти подкаталоги проверяются в дополнение к алгоритмам, заданным в правилах проверки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37a7f-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="37a7f-110">[in] Имя сборки, которую необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="37a7f-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="37a7f-111">Формат данной строки, определенные в классе справочника, посвященных <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="37a7f-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="37a7f-112">[in] Массив типа <<!--zzxref:IUnknown --> `IUnknown`> для размещения `IMetadataAssemblyImport` указателей на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="37a7f-112">[in] An array of type <<!--zzxref:IUnknown --> `IUnknown`> in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="37a7f-113">[out] Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="37a7f-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="37a7f-114">[out] Число возвращаемых указателя на интерфейс.</span><span class="sxs-lookup"><span data-stu-id="37a7f-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="37a7f-115">То есть число указателей интерфейса непосредственно в `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="37a7f-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37a7f-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="37a7f-116">Return Value</span></span>  
  
|<span data-ttu-id="37a7f-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37a7f-117">HRESULT</span></span>|<span data-ttu-id="37a7f-118">Описание</span><span class="sxs-lookup"><span data-stu-id="37a7f-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="37a7f-119">`FindAssembliesByName`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="37a7f-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="37a7f-120">Нет ни одна из сборок.</span><span class="sxs-lookup"><span data-stu-id="37a7f-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37a7f-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="37a7f-121">Remarks</span></span>  
 <span data-ttu-id="37a7f-122">Имя сборки, `FindAssembliesByName` метод находит сборку, выполнив стандартные правила для разрешения ссылок на сборки.</span><span class="sxs-lookup"><span data-stu-id="37a7f-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="37a7f-123">(Дополнительные сведения см. в разделе [как среда выполнения находит сборки](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настроить различные аспекты контекста распознавателя, такие как поиск базового и закрытый путь приложения.</span><span class="sxs-lookup"><span data-stu-id="37a7f-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="37a7f-124">`FindAssembliesByName` Методу требуется среда CLR инициализирована в процессе для вызова логики разрешения сборки.</span><span class="sxs-lookup"><span data-stu-id="37a7f-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="37a7f-125">Таким образом, необходимо вызвать метод [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (передача COINITEE_DEFAULT) перед вызовом `FindAssembliesByName`, а затем выполните с помощью вызова [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="37a7f-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="37a7f-126">`FindAssembliesByName`Возвращает [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) указатель файла, содержащего манифест сборки для имени сборки, переданные в.</span><span class="sxs-lookup"><span data-stu-id="37a7f-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="37a7f-127">Если данное имя сборки (например, если он не включает версию) задан не полностью, может возвратить несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="37a7f-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="37a7f-128">`FindAssembliesByName`обычно используется компилятором, который пытается найти сборку во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="37a7f-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a7f-129">Требования</span><span class="sxs-lookup"><span data-stu-id="37a7f-129">Requirements</span></span>  
 <span data-ttu-id="37a7f-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37a7f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37a7f-131">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37a7f-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37a7f-132">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37a7f-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="37a7f-133">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37a7f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a7f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="37a7f-134">See Also</span></span>  
 [<span data-ttu-id="37a7f-135">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="37a7f-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="37a7f-136">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="37a7f-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
