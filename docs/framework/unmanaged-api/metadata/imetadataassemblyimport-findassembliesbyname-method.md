---
title: "Метод IMetaDataAssemblyImport::FindAssembliesByName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d6518fdcf1bef8eaea74818f69f46bb6df26e31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a>Метод IMetaDataAssemblyImport::FindAssembliesByName
Возвращает массив сборок с заданным `szAssemblyName` параметр, с помощью стандартных правил, применяемых средой выполнения (CLR) для разрешения ссылок.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `szAppBase`  
 [in] Корневой каталог, в котором выполняется поиск заданной сборки. Если это значение равно `null`, `FindAssembliesByName` будет осуществлять поиск сборки только в глобальном кэше сборок.  
  
 `szPrivateBin`  
 [in] Список разделенных точкой с запятой каталогов (например, «bin; bin2»), в корневом каталоге, в котором выполняется поиск для сборки. Эти подкаталоги проверяются в дополнение к алгоритмам, заданным в правилах проверки по умолчанию.  
  
 `szAssemblyName`  
 [in] Имя сборки, которую необходимо найти. Формат данной строки, определенные в классе справочника, посвященных <xref:System.Reflection.AssemblyName>.  
  
 `ppIUnk`  
 [in] Массив типа <<!--zzxref:IUnknown --> `IUnknown`> для размещения `IMetadataAssemblyImport` указателей на интерфейс.  
  
 `cMax`  
 [out] Максимальное число указателей интерфейса, которые могут быть помещены в `ppIUnk`.  
  
 `pcAssemblies`  
 [out] Число возвращаемых указателя на интерфейс. То есть число указателей интерфейса непосредственно в `ppIUnk`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|`S_OK`|`FindAssembliesByName`успешно возвращен.|  
|`S_FALSE`|Нет ни одна из сборок.|  
  
## <a name="remarks"></a>Примечания  
 Имя сборки, `FindAssembliesByName` метод находит сборку, выполнив стандартные правила для разрешения ссылок на сборки. (Дополнительные сведения см. в разделе [как среда выполнения находит сборки](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` позволяет вызывающему объекту настроить различные аспекты контекста распознавателя, такие как поиск базового и закрытый путь приложения.  
  
 `FindAssembliesByName` Методу требуется среда CLR инициализирована в процессе для вызова логики разрешения сборки. Таким образом, необходимо вызвать метод [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (передача COINITEE_DEFAULT) перед вызовом `FindAssembliesByName`, а затем выполните с помощью вызова [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).  
  
 `FindAssembliesByName`Возвращает [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) указатель файла, содержащего манифест сборки для имени сборки, переданные в. Если данное имя сборки (например, если он не включает версию) задан не полностью, может возвратить несколько сборок.  
  
 `FindAssembliesByName`обычно используется компилятором, который пытается найти сборку во время компиляции.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
