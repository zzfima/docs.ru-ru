---
title: "Метод IMetaDataImport::FindMember"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a47060575d14e1206e715ea2bfd2ea750bd49c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmember-method"></a>Метод IMetaDataImport::FindMember
Возвращает указатель на MemberDef токен для поля или метода, который заключается в указанном <xref:System.Type> и имеет имя и метаданные указанной подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен TypeDef для класса или интерфейса, включающий элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.  
  
 `szName`  
 [in] Имя элемента для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных элемента.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на токен MemberDef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Для определения члена с помощью его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`). Может существовать несколько членов с тем же именем в классе или интерфейсе. В этом случае передайте сигнатуру члена, чтобы найти уникальное соответствие.  
  
 Подпись, передаваемый `FindMember` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям. Подпись можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить во время выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMember`.  
  
 `FindMember`находит только те элементы, которые были определены непосредственно в классе или интерфейсе; унаследованные члены не найдена.  
  
> [!NOTE]
>  `FindMember`— Это вспомогательный метод. Он вызывает [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не удается найти соответствие, `FindMember` вызывает [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
