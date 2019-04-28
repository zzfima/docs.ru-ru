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
ms.openlocfilehash: 6b388dae0f109ff366f83c92de99b00b80bcc01a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905090"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Метод IMetaDataAssemblyImport::FindAssembliesByName
Возвращает массив сборок с указанным `szAssemblyName` параметр, с помощью стандартных правил, применяемых средой выполнения (CLR) для разрешения ссылок.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parameters"></a>Параметры  
 `szAppBase`  
 [in] Корневой каталог, в котором осуществляется поиск заданной сборки. Если это значение `null`, `FindAssembliesByName` будет искать только в глобальном кэше сборок для сборки.  
  
 `szPrivateBin`  
 [in] Список разделенных точкой с запятой подкаталоги (например, «bin; bin2»), в корневом каталоге, в котором следует искать сборки. В дополнение к указанным в правилах проверки по умолчанию проверяются следующие каталоги.  
  
 `szAssemblyName`  
 [in] Имя сборки для поиска. Формат этой строки определяется в классе справочной странице для <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Массив объектов типа [IUnknown](/cpp/atl/iunknown) для размещения `IMetadataAssemblyImport` указателей на интерфейс.  
  
 `cMax`  
 [out] Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Число возвращаемых указателя на интерфейс. То есть число указателей интерфейса непосредственно в `ppIUnk`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName` успешно возвращен.|  
|`S_FALSE`|Не будут присутствовать сборки.|  
  
## <a name="remarks"></a>Примечания  
 Имя сборки, `FindAssembliesByName` метод находит сборку, выполнив следующие стандартные правила для разрешения ссылок на сборки. (Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настроить различные аспекты контекста распознавателя, такие как путь поиска базового и частных приложений.  
  
 `FindAssembliesByName` Методу требуется быть инициализирована в процессе для вызова логики разрешения сборки среды CLR. Таким образом, необходимо вызвать [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (передавая COINITEE_DEFAULT) перед вызовом `FindAssembliesByName`и выполните с помощью вызова [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName` Возвращает [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) указатель файла, содержащего манифест сборки для имени сборки, передаваемой в. Если указанное имя сборки (например, если он не включает версию) задан не полностью, может быть возвращено несколько сборок.  
  
 `FindAssembliesByName` обычно используется с помощью компилятора, который пытается найти сборку во время компиляции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
