---
title: Метод IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 4a258ce9121a287929ca5bc39c480f1ca2596e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437460"
---
# <a name="imetadataimportgetmethodprops-method"></a>Метод IMetaDataImport::GetMethodProps
Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mb`  
 окне Токен MethodDef, представляющий метод, для которого возвращаются метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер TypeDef, представляющий тип, реализующий метод.  
  
 `szMethod`  
 заполняет Указатель на буфер с именем метода.  
  
 `cchMethod`  
 окне Запрошенный размер `szMethod`.  
  
 `pchMethod`  
 заполняет Указатель на размер в расширенных символах `szMethod`или в случае усечения — фактическое число расширенных символов в имени метода.  
  
 `pdwAttr`  
 заполняет Указатель на любые флаги, связанные с методом.  
  
 `ppvSigBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных метода.  
  
 `pcbSigBlob`  
 заполняет Указатель на размер в байтах `ppvSigBlob`.  
  
 `pulCodeRVA`  
 заполняет Указатель на относительный виртуальный адрес метода.  
  
 `pdwImplFlags`  
 заполняет Указатель на любые флаги реализации метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
