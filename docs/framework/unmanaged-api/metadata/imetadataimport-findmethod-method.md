---
title: Метод IMetaDataImport::FindMethod
ms.date: 03/30/2017
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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177250"
---
# <a name="imetadataimportfindmethod-method"></a>Метод IMetaDataImport::FindMethod
Получает указатель на токен MethodDef для метода, который <xref:System.Type> прилагается указанным и который имеет указанное имя и подпись метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 (в) Токен `mdTypeDef` для типа (класс или интерфейс), который примыкает к поиску участника. Если это `mdTokenNil`значение, то поиск делается для глобальной функции.  
  
 `szName`  
 (в) Название метода поиска.  
  
 `pvSigBlob`  
 (в) Указатель на двоичную подпись метаданных метода.  
  
 `cbSigBlob`  
 (в) Размер байтов `pvSigBlob`.  
  
 `pmb`  
 (ваут) Указатель на соответствующий токен MethodDef.  
  
## <a name="remarks"></a>Remarks  
 Вы указываете метод, используя его`td`прилагающий`szName`класс или интерфейс (`pvSigBlob`), его имя ( ), и дополнительно его подпись ( ). В классе или интерфейсе может быть несколько методов с одинаковым именем. В этом случае, пройти подпись метода, чтобы найти уникальный матч.  
  
 Подпись, `FindMethod` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области. Подпись может вставлять маркер, который определяет класс или тип значения. Токен — это индекс в локальной таблице TypeDef. Нельзя создавать подпись времени выполнения вне контекста текущей области и использовать `FindMethod`эту подпись в качестве ввода для ввода.  
  
 `FindMethod`находит только методы, которые были определены непосредственно в классе или интерфейсе; он не находит унаследованных методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Reflection.MethodInfo>
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
