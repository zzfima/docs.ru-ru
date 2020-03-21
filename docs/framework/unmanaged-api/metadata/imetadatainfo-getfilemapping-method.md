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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175269"
---
# <a name="imetadatainfogetfilemapping-method"></a>Метод IMetaDataInfo::GetFileMapping
Получает область памяти отображенный файл и тип отображения.  
  
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
 (ваут) Указатель на начало отображаемого файла.  
  
 `pcbData`  
 (ваут) Размер отображенный регион. Если `pdwMappingType` `fmFlat`это так, то это размер файла.  
  
 `pdwMappingType`  
 (ваут) Значение [CorFileMapping,](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) которое указывает тип отображения. Текущая реализация общего времени выполнения языка (CLR) всегда возвращается. `fmFlat` Другие значения зарезервированы для использования в будущем. Однако всегда следует проверять возвращенное значение, поскольку другие значения могут быть включены в будущих версиях или выпусках служб.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Все выходы заполнены.|  
|`E_INVALIDARG`|NULL был принят в качестве аргумента значение.|  
|`COR_E_NOTSUPPORTED`|Реализация CLR не может предоставить информацию о области памяти. Это может происходить по следующим причинам:<br /><br /> - Область метаданных была `ofWrite` открыта `ofCopyMemory` с флагом или флагом.<br />- Область метаданных была `ofReadOnly` открыта без флага.<br />- [Метод IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) использовался для открытия только части метаданных файла.<br />- Файл не является портативным исполняемым (PE) файлом. **Примечание:**  Эти условия зависят от реализации CLR и, вероятно, будут ослаблены в будущих версиях CLR.|  
  
## <a name="remarks"></a>Remarks  
 Память, `ppvData` на которую указывает, действительна только до тех пор, пока открыта базовая область метаданных.  
  
 Для того, чтобы этот метод работал, при составлении карты метаданных дискового файла в память, позвонив `ofReadOnly` в [метод IMetaDataDispenser::OpenScope,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) необходимо указать флаг, и вы не должны указывать флаг `ofWrite` или `ofCopyMemory` флаг.  
  
 Выбор типа картирования файлов для каждой области специфичен для данной реализации CLR. Он не может быть установлен пользователем. Текущая реализация CLR всегда `fmFlat` `pdwMappingType`возвращается в , но это может измениться в будущих версиях CLR или в будущих релизах службы данной версии. Вы всегда должны проверить `pdwMappingType`возвращенное значение в, потому что различные типы будут иметь различные макеты и смещения.  
  
 Прохождение NULL по любому из трех параметров не поддерживается. Метод возвращается, `E_INVALIDARG`и ни один из выходов не заполнен. Игнорирование типа отображения или размера региона может привести к ненормальному прекращению программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [Перечисление CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
