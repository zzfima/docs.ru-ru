---
title: "Метод IMetaDataInfo::GetFileMapping"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f974230dc5ddf2a663f05fc06850f49f1de6e773
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatainfogetfilemapping-method"></a>Метод IMetaDataInfo::GetFileMapping
Возвращает область памяти сопоставленных файлов и тип сопоставления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppvData`  
 [out] Указатель на начало сопоставленный файл.  
  
 `pcbData`  
 [out] Размер сопоставленной области. Если `pdwMappingType` — `fmFlat`, размер файла.  
  
 `pdwMappingType`  
 [out] Объект [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) значение, указывающее тип сопоставления. Текущая реализация среды common language runtime (CLR) всегда возвращает `fmFlat`. Другие значения зарезервированы для будущего использования. Тем не менее следует всегда проверять возвращаемое значение, поскольку другие значения могут быть включены в будущих версиях или в наборах исправлений.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|`S_OK`|Все выходные данные заполняются.|  
|`E_INVALIDARG`|NULL был передан в качестве значения аргумента.|  
|`COR_E_NOTSUPPORTED`|В реализации CLR не может предоставить сведения об области памяти. Это может происходить по следующим причинам:<br /><br /> -Области метаданных была открыта с `ofWrite` или `ofCopyMemory` флаг.<br />-Области метаданных был открыт без `ofReadOnly` флаг.<br />- [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) метода, использовавшегося для открытия только метаданные части файла.<br />-Файл не является файлом переносимого исполняемого (PE). **Примечание:** эти условия зависят от реализации CLR, а скорее всего, будут ослабляется в будущих версиях среды CLR.|  
  
## <a name="remarks"></a>Примечания  
 Объем памяти, `ppvData` указывает допустим только при условии, что открыт базовой области метаданных.  
  
 В этот метод для работы, при сопоставлении метаданных из файла на диске в память, вызвав [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) метод, необходимо указать `ofReadOnly` флаг, а также не указать `ofWrite` или `ofCopyMemory` флаг.  
  
 Выбор типа сопоставления файлов для каждой области относится к заданной реализации среды CLR. Его нельзя установить для пользователя. Текущая реализация среды CLR всегда возвращает `fmFlat` в `pdwMappingType`, но это может измениться в будущих версиях среды CLR или в будущих выпусках данной версии службы. Всегда следует проверять возвращаемое значение `pdwMappingType`, так как различные типы будут иметь разные макеты и смещения.  
  
 Передача значения NULL для любого из трех параметров не поддерживается. Метод возвращает `E_INVALIDARG`, и ни один из выходов заполняются. Игнорирование типа сопоставления или размер области может вызвать аварийное завершение программы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataInfo](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [Перечисление CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
