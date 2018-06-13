---
title: Метод IMetaDataAssemblyImport::EnumFiles
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a1995ed0b281978b45b01dbeda54b02094a30412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445743"
---
# <a name="imetadataassemblyimportenumfiles-method"></a>Метод IMetaDataAssemblyImport::EnumFiles
Перечисляет файлы, на которые ссылается манифест текущей сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть значение null при первом вызове этого метода.  
  
 `rFiles`  
 [out] Массив, используемый для хранения `mdFile` токены метаданных.  
  
 `cMax`  
 [in] Максимальное число `mdFile` маркеры, которые могут быть помещены в `rFiles`.  
  
 `pcTokens`  
 [out] Число `mdFile` токены непосредственно в `rFiles`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumFiles` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcTokens` присваивается нулевое значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
