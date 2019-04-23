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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c6a9473a698e4635c8b5cc9fb58963334dfd65e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081797"
---
# <a name="imetadatainfogetfilemapping-method"></a>Метод IMetaDataInfo::GetFileMapping
Получает область памяти, сопоставленного файла и тип сопоставления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppvData`  
 [out] Указатель на начало сопоставленный файл.  
  
 `pcbData`  
 [out] Размер области, отображаемой. Если `pdwMappingType` является `fmFlat`, размер файла.  
  
 `pdwMappingType`  
 [out] Объект [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) значение, указывающее тип сопоставления. Текущая реализация общеязыковой среды выполнения (CLR) всегда возвращает `fmFlat`. Другие значения зарезервированы для использования в будущем. Тем не менее следует всегда проверять возвращаемое значение, так как другие значения могут быть включены в будущих версиях или в наборах исправлений.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|Все выходные данные заполняются.|  
|`E_INVALIDARG`|Значение NULL был передан в качестве значения аргумента.|  
|`COR_E_NOTSUPPORTED`|Реализация CLR не может предоставить сведения об области памяти. Это может произойти по следующим причинам:<br /><br /> -Область метаданных был открыт с помощью `ofWrite` или `ofCopyMemory` флаг.<br />-Область метаданных был открыт без `ofReadOnly` флаг.<br />- [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метод, использованный для открытия только раздел метаданных файла.<br />— Файл не является файлом переносимого исполняемого (PE). **Примечание.**  Эти условия зависят от реализации CLR и, скорее всего быть ослаблена в будущих версиях среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Память, `ppvData` точек является допустимым, только, пока открыта область базовых метаданных.  
  
 Чтобы этот метод работал, при сопоставлении метаданные файла на диске в память, вызвав [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) метод, необходимо указать `ofReadOnly` флаг, а также не указать `ofWrite` или `ofCopyMemory` флаг.  
  
 Выбор типа файла сопоставления для каждой области относится только к определенной реализации среды CLR. Его нельзя установить для пользователя. Текущая реализация среды CLR всегда возвращает `fmFlat` в `pdwMappingType`, но это может измениться в будущих версиях среды CLR, и в последующих выпусков служб данной версии. Следует всегда проверяйте возвращаемое значение `pdwMappingType`, так как разные типы будут имеют разные макеты и смещения.  
  
 Передача значения NULL для любого из трех параметров не поддерживается. Этот метод возвращает `E_INVALIDARG`, и ни один из выходных данных не будут заполнены. Игнорирование типа сопоставления или размер выделяемой области может вызвать аварийное завершение программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [Перечисление CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
