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
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442326"
---
# <a name="imetadatadispenseropenscope-method"></a>Метод IMetaDataDispenser::OpenScope
Открывает существующий файл на диске и сопоставляет его метаданные с памятью.  
  
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
 окне Имя открываемого файла. Файл должен содержать метаданные среды CLR.  
  
 `dwOpenFlags`  
 окне Значение перечисления [коропенфлагс](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) , определяющее режим (чтение, запись и т. д.) для открытия.  
  
 `riid`  
 окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для импорта (чтения) или выдачи (записи) метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "import" или "Emit". Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.  
  
 `ppIUnk`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="remarks"></a>Заметки  
 Копию метаданных в памяти можно запросить с помощью методов из одного из интерфейсов "Импорт" или добавить к методам из одного из интерфейсов "выдачи".  
  
 Если целевой файл не содержит метаданные CLR, метод `OpenScope` завершится ошибкой.  
  
 В .NET Framework версии 1,0 и 1,1, если область открыта с `dwOpenFlags` установлен в значение Офреад, она может предоставлять общий доступ. То есть, если последующие вызовы `OpenScope` передают имя ранее открытого файла, существующая область используется повторно, а новый набор структур данных не создается. Тем не менее проблемы могут возникать из-за этого общего доступа.  
  
 В .NET Framework версии 2,0 области, открытые с `dwOpenFlags` установленным в Офреад, больше не являются общими. Используйте значение Офреадонли, чтобы разрешить общий доступ к области. При совместном использовании области запросы, использующие интерфейсы метаданных для чтения и записи, завершатся ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataDispenser](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
