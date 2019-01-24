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
ms.openlocfilehash: 68cac76a83164e24c0810c9d19fa845c8580b1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637254"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Метод IMetaDataImport::GetCustomAttributeByName
Получает настраиваемый атрибут, учитывая его название и владельца.  
  
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
 [in] Токен метаданных, представляющий объект, которому принадлежит настраиваемого атрибута.  
  
 `szName`  
 [in] Имя настраиваемого атрибута.  
  
 `ppData`  
 [out] Указатель на массив данных, который является значением настраиваемого атрибута.  
  
 `pcbData`  
 [out] Размер в байтах данных, возвращаемых в *`ppData`.  
  
## <a name="remarks"></a>Примечания  
 Можно определить несколько настраиваемых атрибутов для того же владельца; они могут даже совпадать. Тем не менее `GetCustomAttributeByName` возвращает только один экземпляр. (`GetCustomAttributeByName` возвращает первый обнаруженный экземпляр.) Чтобы найти все экземпляры настраиваемого атрибута, вызовите [IMetaDataImport::EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
