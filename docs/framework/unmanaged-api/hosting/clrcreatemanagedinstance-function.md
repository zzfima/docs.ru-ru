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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131987"
---
# <a name="clrcreatemanagedinstance-function"></a>Функция ClrCreateManagedInstance
Создает экземпляр указанного управляемого типа.  
  
 Эта функция является устаревшей в .NET Framework 4. Используйте активацию COM для создания экземпляра управляемого типа или используйте размещение (см. Дополнительные сведения о [интерфейсах размещения CLR, добавленных в .NET Framework 4 и 4,5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pTypeName`  
 окне Указатель на имя запрашиваемого типа экземпляра.  
  
 `riid`  
 окне `IID` запрашиваемого типа экземпляра.  
  
 `ppObject`  
 заполняет Указатель на указатель на экземпляр управляемого типа, запрошенный вызывающим объектом.  
  
## <a name="remarks"></a>Заметки  
 Среда CLR уже должна быть загружена в процесс. Например, его можно загрузить с помощью вызова функции [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) перед вызовом функции `ClrCreateManagedInstance`. Если среда выполнения не загружена, `ClrCreateManagedInstance` сначала пытается загрузить v 1.0.3705 среды выполнения. В случае сбоя он пытается загрузить последнюю версию среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
