---
title: Метод IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc16d01d45364d1a17f281f859b27c3e48342ff0
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835724"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Метод IMetaDataImport::GetInterfaceImplProps
Возвращает указатель на токены метаданных для <xref:System.Type> , реализующий заданный метод, и для интерфейса, который объявляет этот метод.
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `iiImpl`  
 [in] Токен метаданных, представляющий метод для возврата маркеров для класса и интерфейса.  
  
 `pClass`  
 [out] Токен метаданных, представляющий класс, который реализует метод.  
  
 `ptkIface`  
 [out] Токен метаданных, представляющий интерфейс, определяющий метод, реализованный.  

## <a name="remarks"></a>Примечания

 Получить значение для `iImpl` путем вызова [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) метод.
 
 Например, предположим, что класс содержит `mdTypeDef` token значением 0x02000007 и что он реализует три интерфейсы, типы которых имеют токенов: 

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

По существу эта информация хранится в таблицу реализации интерфейса, как:

| Номер строки | Маркер класса | Токен интерфейса |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Помните, что маркер является 4-байтовое значение:

- Нижние 3 байта содержат номер строки, или удалить.
- Старшему байту содержит тип токена — 0x09 для `mdtInterfaceImpl`.

`GetInterfaceImplProps` Возвращает данные, хранящиеся в строке, маркер которого вами в `iImpl` аргумент. 
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
