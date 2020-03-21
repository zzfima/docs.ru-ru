---
title: Метод IMetaDataDispenser::OpenScopeOnMemory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175932"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>Метод IMetaDataDispenser::OpenScopeOnMemory
Открывает область памяти, содержащую существующие метаданные. То есть этот метод открывает заданную область памяти, в которой существующие данные рассматриваются как метаданные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pData`  
 (в) Указатель, обоужаемый начальный адрес области памяти.  
  
 `cbData`  
 (в) Размер области памяти, байтов.  
  
 `dwOpenFlags`  
 (в) Значение значения [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисления указать режим (читать, писать и так далее) для открытия.  
  
 `riid`  
 (в) IID желаемого интерфейса метаданных, который должен быть возвращен; абонент будет использовать интерфейс для импорта (чтения) или испускателя (записи) метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "импорт" или "излучать". Действительные значения— IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 или IID_IMetaDataImport2.  
  
 `ppIUnk`  
 (ваут) Указатель на возвращенный интерфейс.  
  
## <a name="remarks"></a>Remarks  
 Копия метаданных в памяти может быть запрошена с помощью методов одного из «импортных» интерфейсов или добавлена к методам одного из интерфейсов «излучать».  
  
 Метод `OpenScopeOnMemory` аналогичен [методу IMetaDataDispenser::OpenScope,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) за исключением того, что метаданные, представляющие интерес, уже существуют в памяти, а не в файле на диске.  
  
 Если целевая область памяти не содержит метаданных общего времени `OpenScopeOnMemory` выполнения языка (CLR), метод выйдет из строя.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).  
  
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
