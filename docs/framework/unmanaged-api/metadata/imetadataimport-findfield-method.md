---
title: "Метод IMetaDataImport::FindField"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2178f8738ca510fb2163c1043dd94ebcb7043904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindfield-method"></a>Метод IMetaDataImport::FindField
Возвращает указатель на FieldDef токен для поля, которое заключено в указанном <xref:System.Type> и имеет имя и метаданные указанной подписи.  
  
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
 [in] Токен TypeDef для класса или интерфейса, содержащего поля для поиска. Если это значение равно `mdTokenNil`, поиск выполняется в глобальной переменной.  
  
 `szName`  
 [in] Имя поля для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных поля.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на токен FieldDef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Укажите поля, используя его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).  
  
 Подпись, передаваемый `FindField` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям. Подпись можно внедрить токен, который определяет включающего класса или типа значения. (Маркер — это индекс в локальной таблице TypeDef). Не удается построить во время выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindField`.  
  
 `FindField`находит только поля, которые были определены непосредственно в классе или интерфейсе; наследуемые поля не найден.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
