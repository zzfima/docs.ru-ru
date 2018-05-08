---
title: Метод IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdb9e91f5e7dfe8d54fb50c757684117465944df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportenumpermissionsets-method"></a>Метод IMetaDataImport::EnumPermissionSets
Перечисляет разрешения для объектов в указанной области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `tk`  
 [in] Токен метаданных, который ограничивает область поиска, или значение NULL для поиска возможных широкой области.  
  
 `dwActions`  
 [in] Флаги представляющий <xref:System.Security.Permissions.SecurityAction> значений для включения в `rPermission`, или ноль для возвращения всех действий.  
  
 `rPermission`  
 [out] Массив, используемый для хранения токенов разрешение.  
  
 `cMax`  
 [in] Максимальный размер массива `rPermission`.  
  
 `pcTokens`  
 [out] Число маркеров разрешение, возвращаемых в `rPermission`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
