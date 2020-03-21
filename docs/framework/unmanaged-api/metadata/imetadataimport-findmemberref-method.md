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
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175425"
---
# <a name="imetadataimportfindmemberref-method"></a>Метод IMetaDataImport::FindMemberRef
Получает указатель на токен MemberRef для ссылки участника, <xref:System.Type> которая прилагается указанным и имеет указанное имя и подпись метаданных.  
  
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
 (в) Токен TypeRef для класса или интерфейса, который примыкает к поиску участника. Если это `mdTokenNil`значение, то поиск выполняется для глобальной переменной или глобальной функциональной ссылки.  
  
 `szName`  
 (в) Имя участника ссылки на поиск.  
  
 `pvSigBlob`  
 (в) Указатель на двоичную подпись метаданных ссылки участника.  
  
 `cbSigBlob`  
 (в) Размер байтов `pvSigBlob`.  
  
 `pmr`  
 (ваут) Указатель на соответствующий токен MemberRef.  
  
## <a name="remarks"></a>Remarks  
 Вы указываете участника, используя его`td`прилагающий`szName`класс или интерфейс (), его имя (), и по желанию его подпись ().`pvSigBlob`  
  
 Подпись, `FindMemberRef` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области. Подпись может вставлять маркер, который определяет класс или тип значения. Токен — это индекс в локальной таблице TypeDef. Нельзя создавать подпись времени выполнения вне контекста текущей области и `FindMemberRef`использовать эту подпись в качестве ввода.  
  
 `FindMemberRef`находит только ссылки членов, которые были определены непосредственно в классе или интерфейсе; он не находит унаследованных ссылок членов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
