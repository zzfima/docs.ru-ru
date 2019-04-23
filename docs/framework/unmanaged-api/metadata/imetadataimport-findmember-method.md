---
title: Метод IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63afd82ca88e1a7c61913ec7fcc4d77d03ae9927
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183174"
---
# <a name="imetadataimportfindmember-method"></a>Метод IMetaDataImport::FindMember
Возвращает указатель на MemberDef токен для поля или метода, который заключен заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.  
  
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
  
## <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен TypeDef для класса или интерфейса, который окружает элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.  
  
 `szName`  
 [in] Имя элемента для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных элемента.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на токен MemberDef сопоставления.  
  
## <a name="remarks"></a>Примечания  
 Для определения члена с помощью его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`). Может существовать несколько членов с одинаковыми именами в классе или интерфейсе. В этом случае следует передайте сигнатуре члена, чтобы найти уникальное соответствие.  
  
 Подпись передается `FindMember` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области. Подписи можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMember`.  
  
 `FindMember` находит только те элементы, которые были определены непосредственно в классе или интерфейсе; унаследованные члены не найден.  
  
> [!NOTE]
>  `FindMember` — Это вспомогательный метод. Он вызывает [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не удается найти соответствие, `FindMember` затем вызывает [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
