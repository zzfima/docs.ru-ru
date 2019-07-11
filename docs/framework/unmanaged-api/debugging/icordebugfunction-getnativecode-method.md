---
title: Метод ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754598"
---
# <a name="icordebugfunctiongetnativecode-method"></a>Метод ICorDebugFunction::GetNativeCode
Получает машинный код для функции, представленного данным экземпляром ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppCode`  
 [out] Указатель на интерфейс ICorDebugCode экземпляр, который представляет машинный код для этой функции, или значение null, если эта функция представляет код MSIL (MSIL), не был just-in-time (JIT) компиляции.  
  
## <a name="remarks"></a>Примечания  
 Если функция, которая представляется этим `ICorDebugFunction` экземпляр был JIT-компиляции более одного раза, как в случае универсальных типов `GetNativeCode` возвращает объект случайных машинного кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
