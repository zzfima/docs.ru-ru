---
title: "Метод IMetaDataImport::GetPropertyProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc3a1ce1d07bda50b2b578e7d20870324d60edc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
  
#### <a name="parameters"></a>Параметры  
 `prop`  
 [in] Токен, представляющий свойства для возврата метаданных.  
  
 `pClass`  
 [out] Указатель на токен TypeDef, который представляет тип, который реализует свойство.  
  
 `szProperty`  
 [out] Буфер для хранения имени свойства.  
  
 `cchProperty`  
 [in] Размер в расширенных символах с `szProperty`.  
  
 `pchProperty`  
 [out] Число расширенных символов, возвращаемых в `szProperty`.  
  
 `pdwPropFlags`  
 [out] Указатель на любой флаги атрибутов, примененных к свойству. Это значение является битовой [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) перечисления.  
  
 `ppvSig`  
 [out] Указатель на подпись метаданных свойства.  
  
 `pbSig`  
 [out] Число байтов, возвращенных в `ppvSig`.  
  
 `pdwCPlusTypeFlag`  
 [out] Флаг, указывающий тип константы, значение свойства по умолчанию. Это значение является из CorElementType перечисление.  
  
 `ppDefaultValue`  
 [out] Указатель на байты, сохранить значения по умолчанию для этого свойства.  
  
 `pcchDefaultValue`  
 [out] Размер в расширенных символах с `ppDefaultValue`, если `pdwCPlusTypeFlag` не является соответствующим; в противном случае это значение не применимо. В этом случае длина `ppDefaultValue` выводится из типа, который задается параметром `pdwCPlusTypeFlag`.  
  
 `pmdSetter`  
 [out] Указатель на токен MethodDef, представляющий метод доступа set для свойства.  
  
 `pmdGetter`  
 [out] Указатель на токен MethodDef, представляющий метод доступа get для свойства.  
  
 `rmdOtherMethod`  
 [out] Массив токены MethodDef, представляющие другие методы, связанные со свойством.  
  
 `cMax`  
 [in] Максимальный размер массива `rmdOtherMethod`. Если не указать массив недостаточно велик для хранения всех методов, они пропускаются без предупреждения.  
  
 `pcOtherMethod`  
 [out] Число токены MethodDef, возвращаемых в `rmdOtherMethod`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
