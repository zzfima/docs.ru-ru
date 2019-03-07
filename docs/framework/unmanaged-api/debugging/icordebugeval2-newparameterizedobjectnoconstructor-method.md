---
title: Метод ICorDebugEval2::NewParameterizedObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6feef7b1e1f09107cd2a57555df07bebec86effa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466990"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a>Метод ICorDebugEval2::NewParameterizedObjectNoConstructor
Создает новый объект параметризованного типа указанного класса не пытается вызвать метод-конструктор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 [in] Указатель на объект ICorDebugClass, который представляет класс для создания экземпляра объекта.  
  
 `nTypeArgs`  
 [in] Передано число аргументов типа.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект, представляющий аргумент типа для объекта, экземпляр которого создается ICorDebugType.  
  
## <a name="remarks"></a>Примечания  
 `NewParameterizedObjectNoConstructor` Метод завершится ошибкой, если неверное число аргументов типа, или неправильный типы аргументов типа передаются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
