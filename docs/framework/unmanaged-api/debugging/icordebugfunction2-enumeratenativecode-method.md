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
ms.openlocfilehash: fb7e2ed7b076cfa20064902b3592c8f958efc0ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917049"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>Метод ICorDebugFunction2::EnumerateNativeCode
Возвращает указатель интерфейса на объект Икордебугкодинум, содержащий операторы машинного кода в функции, на которую ссылается этот объект ICorDebugFunction2.  
  
> [!NOTE]
> `EnumerateNativeCode`не реализован в текущей версии .NET Framework.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorDebug. idl, CorDebug. h
