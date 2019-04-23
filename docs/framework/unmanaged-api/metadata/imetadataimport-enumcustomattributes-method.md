---
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b80bb7b62d3a4ffee61cc6756b7d7d02f2b074bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196207"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Метод IMetaDataImport::EnumCustomAttributes
Перечисляет токены определений настраиваемых атрибутов, связанных с указанным типом или членом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на возвращенном перечислителе.  
  
 `tk`  
 [in] Маркер в рамках перечисление, или ноль для всех настраиваемых атрибутов.  
  
 `tkType`  
 [in] Маркер для конструктора типа атрибутов, которые необходимо перечислить или `null` для всех типов.  
  
 `rCustomAttributes`  
 [out] Массив настраиваемых атрибутов маркеров.  
  
 `cMax`  
 [in] Максимальный размер массива `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, optional] Фактическое число маркеров значения, возвращаемые в `rCustomAttributes`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` успешно возвращен.|  
|`S_FALSE`|Нет никаких настраиваемых атрибутов для перечисления. В этом случае `pcCustomAttributes` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
