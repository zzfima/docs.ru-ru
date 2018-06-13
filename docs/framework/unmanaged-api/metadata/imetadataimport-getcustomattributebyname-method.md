---
title: Метод IMetaDataImport::GetCustomAttributeByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c25304bef4d240eedea749bb2829595056f9b74d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449251"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Метод IMetaDataImport::GetCustomAttributeByName
Получает настраиваемый атрибут, ее имя и владельца.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tkObj`  
 [in] Токен метаданных, представляющий объект, которому принадлежит пользовательский атрибут.  
  
 `szName`  
 [in] Имя настраиваемого атрибута.  
  
 `ppData`  
 [out] Указатель на массив данных, который является значением настраиваемого атрибута.  
  
 `pcbData`  
 [out] Размер в байтах данных, возвращаемых в *`ppData`.  
  
## <a name="remarks"></a>Примечания  
 Можно определить несколько настраиваемых атрибутов для того же владельца; они могут даже имеют то же имя. Тем не менее `GetCustomAttributeByName` возвращает только один экземпляр. (`GetCustomAttributeByName` возвращает первый экземпляр, расположенного.) Чтобы найти все вхождения настраиваемый атрибут, вызовите [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
