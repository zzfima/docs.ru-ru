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
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175451"
---
# <a name="imetadataimportenumpermissionsets-method"></a>Метод IMetaDataImport::EnumPermissionSets
Перечисляет разрешения для объектов в указанной области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 (в, вне) Указатель на регистратор. Это должно быть NULL для первого вызова этого метода.  
  
 `tk`  
 (в) Токен метаданных, ограничивающий область поиска, или NULL для поиска максимально возможного объема.  
  
 `dwActions`  
 (в) Флаги, <xref:System.Security.Permissions.SecurityAction> представляющие значения `rPermission`для включения в , или ноль, чтобы вернуть все действия.  
  
 `rPermission`  
 (ваут) Массив, используемый для хранения токенов Разрешения.  
  
 `cMax`  
 [in] Максимальный размер массива `rPermission`.  
  
 `pcTokens`  
 (ваут) Число токенов Разрешения, `rPermission`возвращенных в .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`вернулся успешно.|  
|`S_FALSE`|Нет токенов для перечисления. В этом `pcTokens` случае, равна нулю.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
