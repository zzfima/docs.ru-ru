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
ms.openlocfilehash: c12d3a7a7d1e52529435361aa12e22e4edeecf03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448292"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Метод IMetaDataAssemblyImport::FindAssembliesByName
Возвращает массив сборок с указанным параметром `szAssemblyName`, используя стандартные правила, используемые средой CLR для разрешения ссылок.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parameters"></a>Параметры  
 `szAppBase`  
 окне Корневой каталог, в котором выполняется поиск данной сборки. Если это значение равно `null`, `FindAssembliesByName` будет искать сборку только в глобальном кэше сборок.  
  
 `szPrivateBin`  
 окне Список подкаталогов, разделенных точкой с запятой (например, "bin; BIN2"), в корневом каталоге, в котором выполняется поиск сборки. Эти каталоги проверяются в дополнение к тем, которые указаны в правилах проверки по умолчанию.  
  
 `szAssemblyName`  
 окне Имя искомой сборки. Формат этой строки определяется на странице ссылки на класс для <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 окне Массив типа [IUnknown](/cpp/atl/iunknown) , в который помещаются указатели интерфейса `IMetadataAssemblyImport`.  
  
 `cMax`  
 заполняет Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk`.  
  
 `pcAssemblies`  
 заполняет Число возвращаемых указателей на интерфейс. То есть число указателей интерфейса, фактически помещенных в `ppIUnk`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` успешно возвращено.|  
|`S_FALSE`|Нет сборок.|  
  
## <a name="remarks"></a>Заметки  
 При наличии имени сборки метод `FindAssembliesByName` находит сборку, следуя стандартным правилам разрешения ссылок на сборки. (Дополнительные сведения см. [в разделе Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настраивать различные аспекты контекста сопоставителя сборок, такие как базовый и частный путь поиска приложения.  
  
 Метод `FindAssembliesByName` требует инициализации среды CLR в процессе для вызова логики разрешения сборки. Поэтому необходимо вызвать [CoInitialize](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (передав COINITEE_DEFAULT) перед вызовом `FindAssembliesByName`, а затем выполнить вызов [каунинитиализекор](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` возвращает указатель [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) на файл, содержащий манифест сборки для переданного имени сборки. Если заданное имя сборки не указано полностью (например, если оно не включает версию), может возвращаться несколько сборок.  
  
 `FindAssembliesByName` часто используется компилятором, который пытается найти ссылочную сборку во время компиляции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
