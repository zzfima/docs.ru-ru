---
title: Метод IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e6e53f69f58c2f5778083d9b8f8be466b952cdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777953"
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
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [in, out] Указатель на перечислитель. Это должно быть NULL при первом вызове этого метода.  
  
 `rMethods`  
 [out] Массив, используемый для хранения токенов MemberDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rMethods`.  
  
 `pcTokens`  
 [out] Число возвращенных в токены MemberDef `rMethods`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` успешно возвращен.|  
|`S_FALSE`|Существуют маркеры для перечисления отсутствуют. В этом случае `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Неразрешенный метод — это приложения, был объявлен, но не реализован. Метод включается в перечисление, если метод помечен `miForwardRef` и либо `mdPinvokeImpl` или `miRuntime` присваивается нулевое значение. Другими словами, неразрешенный метод является методом класса, помеченного `miForwardRef` , но который не реализован в неуправляемом коде (посредством PInvoke) и не реализуются внутренним образом средой в самой среде выполнения  
  
 Перечисление исключает все методы, определенные в области модуля (глобальные) или в интерфейсы или абстрактные классы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
