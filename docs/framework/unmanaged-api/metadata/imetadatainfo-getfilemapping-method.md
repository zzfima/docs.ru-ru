---
title: Метод IMetaDataInfo::GetFileMapping
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436172"
---
# <a name="imetadatainfogetfilemapping-method"></a>Метод IMetaDataInfo::GetFileMapping
Возвращает область памяти сопоставленного файла и тип сопоставления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppvData`  
 заполняет Указатель на начало сопоставленного файла.  
  
 `pcbData`  
 заполняет Размер сопоставленной области. Если `pdwMappingType` `fmFlat`, то это размер файла.  
  
 `pdwMappingType`  
 заполняет Значение [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) , указывающее тип сопоставления. Текущая реализация среды CLR всегда возвращает `fmFlat`. Другие значения зарезервированы для использования в будущем. Однако всегда следует проверять возвращаемое значение, так как в будущих версиях или выпусках служб могут быть включены другие значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Все выходные данные заполнены.|  
|`E_INVALIDARG`|Значение NULL передано в качестве значения аргумента.|  
|`COR_E_NOTSUPPORTED`|Реализация CLR не может предоставить сведения о области памяти. Это может происходить по следующим причинам:<br /><br /> — Область метаданных была открыта с флагом `ofWrite` или `ofCopyMemory`.<br />— Область метаданных была открыта без флага `ofReadOnly`.<br />— Метод [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части файла с метаданными.<br />— Файл не является переносимым исполняемым файлом (PE). **Примечание.**  Эти условия зависят от реализации CLR и, скорее всего, будут ослаблены в будущих версиях среды CLR.|  
  
## <a name="remarks"></a>Заметки  
 Память, на которую `ppvData` указывает, действительна только при условии, что базовая область метаданных открыта.  
  
 Чтобы этот метод работал, при сопоставлении метаданных файла на диске с памятью путем вызова метода [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) необходимо указать флаг `ofReadOnly` и не указывать `ofWrite` или флаг `ofCopyMemory`.  
  
 Выбранный тип сопоставления файлов для каждой области зависит от конкретной реализации среды CLR. Он не может быть задан пользователем. Текущая реализация CLR всегда возвращает `fmFlat` в `pdwMappingType`, но это может измениться в будущих версиях CLR или в будущих выпусках данной версии службы. Всегда следует проверять возвращаемое значение в `pdwMappingType`, поскольку разные типы будут иметь разные макеты и смещения.  
  
 Передача значения NULL для любого из трех параметров не поддерживается. Метод возвращает `E_INVALIDARG`, и ни один из выходных данных не заполнен. Пропуск типа сопоставления или размера региона может привести к аварийному завершению программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [Перечисление CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
