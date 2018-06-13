---
title: Метод IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3736d604b7e77028a2b99d462d88ae207df926c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448027"
---
# <a name="imetadataimportfindmemberref-method"></a>Метод IMetaDataImport::FindMemberRef
Возвращает указатель на токен MemberRef для члена, то есть ссылки, заключенных в указанный <xref:System.Type> и имеет имя и метаданные указанной подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Лексема TypeRef для класса или интерфейса, включающий ссылку на элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или ссылка глобальной функции.  
  
 `szName`  
 [in] Имя члена ссылки для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных для ссылки на член.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmr`  
 [out] Указатель на токен MemberRef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Для определения члена с помощью его включающего класса или интерфейса (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).  
  
 Подпись, передаваемый `FindMemberRef` должны были созданы в текущей области, поскольку подписи привязаны к определенным областям. Подпись можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить во время выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindMemberRef`.  
  
 `FindMemberRef` находит только ссылок на элементы, определенные непосредственно в классе или интерфейсе. не удается найти ссылок на унаследованные члены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
