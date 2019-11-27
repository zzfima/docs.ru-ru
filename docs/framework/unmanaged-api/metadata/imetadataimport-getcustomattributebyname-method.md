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
ms.openlocfilehash: bd7ba7ff10918e5953ea8ae89a60af3115af48a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437681"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Метод IMetaDataImport::GetCustomAttributeByName
Возвращает настраиваемый атрибут по его имени и владельцу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tkObj`  
 окне Токен метаданных, представляющий объект, которому принадлежит настраиваемый атрибут.  
  
 `szName`  
 окне Имя настраиваемого атрибута.  
  
 `ppData`  
 заполняет Указатель на массив данных, являющийся значением настраиваемого атрибута.  
  
 `pcbData`  
 заполняет Размер в байтах данных, возвращаемых в *`ppData`.  
  
## <a name="remarks"></a>Примечания  
 Допускается определение нескольких пользовательских атрибутов для одного и того же владельца; они даже могут иметь одно и то же имя. Однако `GetCustomAttributeByName` возвращает только один экземпляр. (`GetCustomAttributeByName` возвращает первый обнаруженный экземпляр.) Чтобы найти все экземпляры настраиваемого атрибута, вызовите метод [IMetaDataImport:: EnumCustomAttributes](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
