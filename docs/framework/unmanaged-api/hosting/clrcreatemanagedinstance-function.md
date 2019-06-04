---
title: Функция ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67bd6e8a0519d35b867cb525d5ff7730c0459016
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490678"
---
# <a name="clrcreatemanagedinstance-function"></a>Функция ClrCreateManagedInstance
Создает экземпляра указанного управляемого типа.  
  
 Эта функция является устаревшим в .NET Framework 4. Использовать COM-компоненты для создания экземпляра управляемого типа или размещение (см. в разделе [CLR размещение интерфейсов, добавленные в .NET Framework 4 и 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTypeName`  
 [in] Указатель на имя запрашиваемого типа экземпляра.  
  
 `riid`  
 [in] `IID` Запрашиваемого типа экземпляра.  
  
 `ppObject`  
 [out] Указатель на указатель на экземпляр управляемого типа, который был запрошен вызывающим объектом.  
  
## <a name="remarks"></a>Примечания  
 Среда CLR, уже должны быть загружены в процесс. Например, его можно загрузить с помощью вызова [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) функцию перед `ClrCreateManagedInstance` функция вызывается. Если среда выполнения не загружается, `ClrCreateManagedInstance` сначала пытается загрузить v1.0.3705 среды выполнения. Если это не удается, предпринимается попытка загрузить последнюю версию среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
