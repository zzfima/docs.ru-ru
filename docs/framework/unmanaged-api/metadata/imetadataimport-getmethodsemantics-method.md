---
title: Метод IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 0542c518b64764ad27aa00b8d595be1191059436
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437446"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>Метод IMetaDataImport::GetMethodSemantics
Получает флаги, указывающие связь между методом, на который ссылается указанный токен MethodDef, и связанным свойством и событием, на которые ссылается указанный токен Евентпроп.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mb`  
 окне Токен MethodDef, представляющий метод, для которого необходимо получить сведения о семантической роли.  
  
 `tkEventProp`  
 окне Токен, представляющий парное свойство и событие, для которого необходимо получить роль метода.  
  
 `pdwSemanticsFlags`  
 заполняет Указатель на соответствующие флаги семантики. Это значение является битовой маской из перечисления [кормесодсемантиксаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) .  
  
## <a name="remarks"></a>Примечания  
 Метод [IMetaDataEmit::D ефинепроперти](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) задает флаги семантики метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
