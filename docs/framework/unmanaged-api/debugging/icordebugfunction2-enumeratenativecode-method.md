---
title: Метод ICorDebugFunction2::EnumerateNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61dcf014a65f524d2b2e7b92bcc7f007d1a47125
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754511"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>Метод ICorDebugFunction2::EnumerateNativeCode
Получает указатель интерфейса на объект, содержащий инструкции машинного кода в функции, на которые ссылается этот объект ICorDebugFunction2 ICorDebugCodeEnum.  
  
> [!NOTE]
>  `EnumerateNativeCode` не реализован в текущей версии платформы .NET Framework.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorDebug.idl, CorDebug.h
