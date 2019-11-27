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
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437953"
---
# <a name="imetadataimportfindmemberref-method"></a>Метод IMetaDataImport::FindMemberRef
Возвращает указатель на токен MemberRef для ссылки на элемент, заключенный в заданный <xref:System.Type> и имеющий указанное имя и подпись метаданных.  
  
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
 окне Токен TypeRef для класса или интерфейса, который заключает в себя ссылку на элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или ссылки на глобальную функцию.  
  
 `szName`  
 окне Имя искомой ссылки на член.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных ссылки на элемент.  
  
 `cbSigBlob`  
 окне Размер в байтах `pvSigBlob`.  
  
 `pmr`  
 заполняет Указатель на соответствующий токен MemberRef.  
  
## <a name="remarks"></a>Примечания  
 Элемент указывается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и, при необходимости, его сигнатуры (`pvSigBlob`).  
  
 Подпись, передаваемая `FindMemberRef`, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMemberRef`.  
  
 `FindMemberRef` находит только те ссылки на элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные ссылки на члены.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
