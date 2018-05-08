---
title: Метод IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 112ddcf51a5637bb89df9479850c2a4a70d2e1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimport2getversionstring-method"></a>Метод IMetaDataImport2::GetVersionString
Получает номер версии среды выполнения, который использовался для создания сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzBuf`  
 [out] Массив для хранения строки, которое указывает версию.  
  
 `ccBufSize`  
 [in] Размер в расширенные символы из `pwzBuf` массива.  
  
 `pccBufSize`  
 [out] Число расширенных символов, включая значение NULL возвращается в `pwzBuf` массива.  
  
## <a name="remarks"></a>Примечания  
 `GetVersionString` Метод получает версию построения для текущей области метаданных. Если область никогда не сохранялся, не будет построен для версии, и будет возвращена пустая строка.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
