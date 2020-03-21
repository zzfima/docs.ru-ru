---
title: Метод IMetaDataDispenser::OpenScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175945"
---
# <a name="imetadatadispenseropenscope-method"></a>Метод IMetaDataDispenser::OpenScope
Открывает существующий файл на диске и отображает свои метаданные в память.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szScope`  
 (в) Имя файла, которое будет открыто. Файл должен содержать метаданные общего времени выполнения языка (CLR).  
  
 `dwOpenFlags`  
 (в) Значение значения [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления указать режим (читать, писать и так далее) для открытия.  
  
 `riid`  
 (в) IID желаемого интерфейса метаданных, который должен быть возвращен; абонент будет использовать интерфейс для импорта (чтения) или испускателя (записи) метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "импорт" или "излучать". Действительные значения— IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.  
  
 `ppIUnk`  
 (ваут) Указатель на возвращенный интерфейс.  
  
## <a name="remarks"></a>Remarks  
 Копия метаданных в памяти может быть запрошена с помощью методов одного из «импортных» интерфейсов или добавлена к методам одного из интерфейсов «излучать».  
  
 Если целевой файл не содержит метаданных `OpenScope` CLR, метод выйдет из строя.  
  
 В версии .NET Framework 1.0 и версии 1.1, если область открыта с `dwOpenFlags` набором к read, она имеет право на обмен. То есть, если `OpenScope` последующие вызовы передаются во имя файла, который был ранее открыт, существующая область используется повторно и не создается новый набор структур данных. Тем не менее, проблемы могут возникнуть из-за этого обмена.  
  
 В версии .NET Framework 2.0 `dwOpenFlags` области области, открытые с набором ofRead, больше не являются общими. Используйте значение ReadOnly, чтобы можно было поделиться областью. При совместном использовании области запросы, в которых используются интерфейсы метаданных "читать/писать", завершаются неудачей.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
