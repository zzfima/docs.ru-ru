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
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Метод IMetaDataAssemblyImport::FindAssembliesByName
Получает массив сборок с указанным `szAssemblyName` параметром, используя стандартные правила, используемые общим временем выполнения языка (CLR) для решения ссылок.  
  
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
 (в) Корневой каталог, в котором можно найти данную сборку. Если это значение `null`настроено на, `FindAssembliesByName` будет выглядеть только в глобальном кэше сборки для сборки.  
  
 `szPrivateBin`  
 (в) Список субдиректоров, делемых заполколонией (например, "bin;bin2"), в котором можно найти сборку. Эти каталоги проверяются в дополнение к тем, которые указаны в правилах зондирования по умолчанию.  
  
 `szAssemblyName`  
 (в) Название сборки, чтобы найти. Формат этой строки определяется на странице <xref:System.Reflection.AssemblyName>ссылки класса для .  
  
 `ppIUnk`  
 (в) Массив типа [IUnknown,](/cpp/atl/iunknown) в котором `IMetadataAssemblyImport` можно поставить указатели интерфейса.  
  
 `cMax`  
 (ваут) Максимальное количество указателей интерфейса, `ppIUnk`которые могут быть размещены в .  
  
 `pcAssemblies`  
 (ваут) Число указателей интерфейса вернулось. То есть, количество указателей интерфейса `ppIUnk`фактически помещено в .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`вернулся успешно.|  
|`S_FALSE`|Сборок нет.|  
  
## <a name="remarks"></a>Remarks  
 Учитывая имя сборки, `FindAssembliesByName` метод находит сборку, следуя стандартным правилам для разрешения ссылок сборки. (Для получения дополнительной информации, [см. Как Runtime находит сборки](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему настроить различные аспекты контекста разрешения сборки, такие как база приложений и частный путь поиска.  
  
 Метод `FindAssembliesByName` требует, чтобы CLR был инициализирован в процессе, чтобы вызвать логику разрешения сборки. Таким образом, вы должны позвонить [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (проходя COINITEE_DEFAULT) перед вызовом, `FindAssembliesByName`а затем следовать с вызовом [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`возвращает указатель [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) в файл, содержащий манифест сборки для имени сборки, в котором находится передаваемое. Если данное имя сборки не полностью указано (например, если оно не содержит версию), может быть возвращено несколько сборок.  
  
 `FindAssembliesByName`обычно используется компилятором, который пытается найти ссылку сборки во время компиляции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Как Время выполнения находит сборки](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
