---
title: "Метод IMetaDataImport::EnumUnresolvedMethods"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUnresolvedMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3c7709180e5b7811379c25977f8a8d23b91adb3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>Метод IMetaDataImport::EnumUnresolvedMethods
Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `rMethods`  
 [out] Массив, используемый для хранения MemberDef токенов.  
  
 `cMax`  
 [in] Максимальный размер массива `rMethods`.  
  
 `pcTokens`  
 [out] Количество возвращаемых в токены MemberDef `rMethods`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods`успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Неразрешенный метод является один, который объявлен, но не реализован. Метод включается в перечислении, если метод помечен `miForwardRef` и либо `mdPinvokeImpl` или `miRuntime` присваивается нулевое значение. Другими словами, неразрешенный метод является методом класса, помеченного `miForwardRef` , но которой не реализован в неуправляемом коде (посредством PInvoke) не реализуются внутренне самой средой выполнения.  
  
 Перечисление исключает все методы, определенные в области модуля (глобальные) или в интерфейсы или абстрактные классы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
