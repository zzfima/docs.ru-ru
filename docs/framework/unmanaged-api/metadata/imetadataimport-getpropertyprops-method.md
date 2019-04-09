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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122607"
---
# <a name="imetadataimportgetpropertyprops-method"></a>Метод IMetaDataImport::GetPropertyProps
Получает метаданные для свойства, представленного указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
 [in] Токен, который представляет свойство для возврата метаданных.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, представляющий тип, реализующий свойства.  
  
 `szProperty`  
 [out] Буфер для хранения имени свойства.  
  
 `cchProperty`  
 [in] Размер в расширенных символах `szProperty`.  
  
 `pchProperty`  
 [out] Число расширенных символов, возвращаемых в `szProperty`.  
  
 `pdwPropFlags`  
 [out] Указатель на любой флаги атрибутов, примененным к свойству. Это значение является битовой [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) перечисления.  
  
 `ppvSig`  
 [out] Указатель на подпись метаданных свойства.  
  
 `pbSig`  
 [out] Число байтов, возвращаемых в `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, указывающий тип константы, которая является значением по умолчанию свойства. Это значение равно из CorElementType перечисления.  
  
 `ppDefaultValue`  
 [out] Указатель на байты, которые хранят значение по умолчанию для этого свойства.  
  
 `pcchDefaultValue`  
 [out] Размер в расширенных символах `ppDefaultValue`, если `pdwCPlusTypeFlag` является соответствующим; в противном случае это значение неприменимо. В этом случае длина `ppDefaultValue` выводится из типа, который задается параметром `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Указатель на токен MethodDef, представляющий метод доступа set для свойства.  
  
 `pmdGetter`  
 [out] Указатель на токен MethodDef, представляющий метод доступа get свойства.  
  
 `rmdOtherMethod`  
 [out] Массив токены MethodDef, представляющие другие методы, связанные со свойством.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`. Если вы не укажете массив недостаточно велик для хранения всех методов, они пропускаются без предупреждения.  
  
 `pcOtherMethod`  
 [out] Количество токены MethodDef, возвращаемых в `rmdOtherMethod`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
