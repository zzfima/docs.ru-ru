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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175386"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Метод IMetaDataImport::GetInterfaceImplProps
Получает указатель на маркеры метаданных <xref:System.Type> для того, который реализует указанный метод, и для интерфейса, который декларирует этот метод.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iiImpl`  
 (в) Токен метаданных, представляющий метод возврата маркеров класса и интерфейса.  
  
 `pClass`  
 (ваут) Токен метаданных, представляющий класс, реализующий метод.  
  
 `ptkIface`  
 (ваут) Токен метаданных, представляющий интерфейс, определяющий реализованный метод.  

## <a name="remarks"></a>Remarks

 Значение для `iImpl` получения, позвонив в метод [EnumInterfaceImpls.](imetadataimport-enuminterfaceimpls-method.md)

 Например, предположим, что `mdTypeDef` класс имеет значение маркера 0x02000007 и что он реализует три интерфейса, типы которых имеют токены:

- 0x0200003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Концептуально эта информация хранится в таблице реализации интерфейса как:

| Номер строки | Токен класса | Токен интерфейса |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Напомним, токен представляет собой значение 4 байт:

- Нижние 3 байта удерживают рядное число, или RID.
- Верхний байт содержит тип маркера - `mdtInterfaceImpl`0x09 для .

`GetInterfaceImplProps`возвращает информацию, хранявшуюся в `iImpl` строке, токен которой вы предоставляете в споре.
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
