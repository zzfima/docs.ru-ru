---
title: Метод IMetaDataImport::EnumUserStrings
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4be12e46851b11a5e6db60c351094a356fa61f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082949"
---
# <a name="imetadataimportenumuserstrings-method"></a>Метод IMetaDataImport::EnumUserStrings
Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `rStrings`  
 [out] Массив, используемый для хранения токенов строк.  
  
 `cMax`  
 [in] Максимальный размер массива `rStrings`.  
  
 `pcStrings`  
 [out] Число токенов строк, возвращаемых в `rStrings`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcStrings` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Токены строки, создаваемые [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) метод. Этот метод предназначен для использования в обозревателе метаданных, а не с помощью компилятора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
