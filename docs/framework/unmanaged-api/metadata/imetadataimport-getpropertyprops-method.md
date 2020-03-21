---
title: Метод IMetaDataImport::GetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175334"
---
# <a name="imetadataimportgetpropertyprops-method"></a>Метод IMetaDataImport::GetPropertyProps
Получает метаданные для свойства, представленного указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,
   [out] LPCWSTR           szProperty,
   [in]  ULONG             cchProperty,
   [out] ULONG             *pchProperty,
   [out] DWORD             *pdwPropFlags,
   [out] PCCOR_SIGNATURE   *ppvSig,
   [out] ULONG             *pbSig,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,
   [out] mdMethodDef       *pmdGetter,
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,
   [out] ULONG             *pcOtherMethod
);  
```  
  
## <a name="parameters"></a>Параметры  
 `prop`  
 (в) Токен, представляющий свойство для возврата метаданных.  
  
 `pClass`  
 (ваут) Указатель на маркер TypeDef, представляющий тип, реализуемый в свойстве.  
  
 `szProperty`  
 (ваут) Буфер для удержания имени свойства.  
  
 `cchProperty`  
 (в) Размер в широких `szProperty`символов .  
  
 `pchProperty`  
 (ваут) Количество широких символов `szProperty`вернулся в .  
  
 `pdwPropFlags`  
 (ваут) Указатель на любые атрибуты флаги, применяемые к свойству. Это значение битмаска из [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) перечисления.  
  
 `ppvSig`  
 (ваут) Указатель на подпись метаданных свойства.  
  
 `pbSig`  
 (ваут) Количество байтов вернулось в `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 (ваут) Флаг, определяющий тип константы, которая является значением свойства по умолчанию. Это значение из перечисления CorElementType.  
  
 `ppDefaultValue`  
 (ваут) Указатель на байты, которые хранят значение по умолчанию для этого свойства.  
  
 `pcchDefaultValue`  
 (ваут) Размер в широких `ppDefaultValue`символов, если `pdwCPlusTypeFlag` это ELEMENT_TYPE_STRING; в противном случае это значение не имеет значения. В этом случае длина `ppDefaultValue` выводилась из типа, `pdwCPlusTypeFlag`указанного .  
  
 `pmdSetter`  
 (ваут) Указатель на маркер MethodDef, представляющий метод набора доступа для свойства.  
  
 `pmdGetter`  
 (ваут) Указатель на токен MethodDef, представляющий метод получения доступа к свойству.  
  
 `rmdOtherMethod`  
 (ваут) Массив токенов MethodDef, представляющих другие методы, связанные с свойством.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`. Если вы не предоставляете массив достаточно большой, чтобы держать все методы, они пропущены без предупреждения.  
  
 `pcOtherMethod`  
 (ваут) Количество возвращенных токенов MethodDef `rmdOtherMethod`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
