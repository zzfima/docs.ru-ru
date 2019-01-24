---
title: Метод IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b07d75b6a8839f9a223ef2c0be52830e107e4088
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527605"
---
# <a name="imetadataimportfindfield-method"></a>Метод IMetaDataImport::FindField
Возвращает указатель на FieldDef токен для поля, которое заключено заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен TypeDef для класса или интерфейса, который содержит поле для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной.  
  
 `szName`  
 [in] Имя поля для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных поля.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на соответствующий токен FieldDef.  
  
## <a name="remarks"></a>Примечания  
 Укажите поле, используя его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).  
  
 Подпись передается `FindField` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области. Подписи можно внедрить токен, который определяет включающего класса или типа значения. (Маркер — это индекс в локальной таблице TypeDef). Не удается построить выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindField`.  
  
 `FindField` находит только те поля, которые были определены непосредственно в классе или интерфейсе; не удается найти унаследованные поля.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
