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
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959969"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>Метод ICorDebugFunction2::EnumerateNativeCode
Получает указатель интерфейса на объект, содержащий инструкции машинного кода в функции, на которые ссылается этот объект ICorDebugFunction2 ICorDebugCodeEnum.  
  
> [!NOTE]
>  `EnumerateNativeCode` не реализован в текущей версии платформы .NET Framework.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** CorDebug.idl, CorDebug.h
