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
ms.openlocfilehash: 0d446e2b78f41d43aa70f429e23f1f4be22fd799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782497"
---
# <a name="imetadataimportfindmemberref-method"></a>Метод IMetaDataImport::FindMemberRef
Получает указатель на токен MemberRef для члена ссылки, то есть заключены в указанный <xref:System.Type> , с указанной сигнатурой имени и метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 [in] Лексема TypeRef для класса или интерфейса, который содержит ссылку на элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или ссылка глобальной функции.  
  
 `szName`  
 [in] Имя ссылки элемента для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных ссылки на член.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmr`  
 [out] Указатель на токен MemberRef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Для определения члена с помощью его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`).  
  
 Подпись передается `FindMemberRef` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области. Подписи можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить выполнения вне контекста текущей области и использовать ее в качестве входных данных для `FindMemberRef`.  
  
 `FindMemberRef` находит только ссылок на элементы, которые были определены непосредственно в классе или интерфейсе; не удается найти ссылки наследуемый член.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
