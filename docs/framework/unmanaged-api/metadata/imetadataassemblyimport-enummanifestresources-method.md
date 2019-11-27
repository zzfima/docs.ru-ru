---
title: Метод IMetaDataAssemblyImport::EnumManifestResources
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: 2748460826deb422a3851713db11343209fe449a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449551"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a>Метод IMetaDataAssemblyImport::EnumManifestResources
Возвращает указатель на перечислитель для ресурсов, указанных в текущем манифесте сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель. Это значение должно быть null, если метод `EnumManifestResources` вызывается в первый раз.  
  
 `rManifestResources`  
 заполняет Массив, используемый для хранения маркеров метаданных `mdManifestResource`.  
  
 `cMax`  
 окне Максимальное число маркеров `mdManifestResource`, которые могут быть помещены в `rManifestResources`.  
  
 `pcTokens`  
 заполняет Число маркеров `mdManifestResource`, фактически помещаемых в `rManifestResources`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumManifestResources` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае `pcTokens` имеет значение 0.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
