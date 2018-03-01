---
title: "Метод IMetaDataImport::FindMethod"
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
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59cc440ba004545c31d6b25d36cca4fdfb58899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmethod-method"></a>Метод IMetaDataImport::FindMethod
Возвращает указатель на MethodDef, токен для метода, который заключается в указанном <xref:System.Type> и имеет имя и метаданные указанной подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] `mdTypeDef` Маркер типа (класса или интерфейса), включающий элемент для поиска. Если это значение равно `mdTokenNil`, а затем поиск выполняется для глобальной функции.  
  
 `szName`  
 [in] Имя метода для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных метода.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на токен MethodDef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Укажите метод, используя его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`). Может существовать несколько методов с тем же именем в классе или интерфейсе. В этом случае передайте подпись метода, чтобы найти уникальное соответствие.  
  
 Подпись, передаваемый `FindMethod` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям. Подпись можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить во время выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMethod`.  
  
 `FindMethod`находит только те методы, которые были определены непосредственно в классе или интерфейсе; унаследованные методы не найдена.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Reflection.MethodInfo>  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
