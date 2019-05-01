---
title: Метод ICorDebugThread::EnumerateChains
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994049"
---
# <a name="icordebugthreadenumeratechains-method"></a>Метод ICorDebugThread::EnumerateChains
Получает указатель интерфейса на перечислитель ICorDebugChainEnum, содержащий всех цепочек стека в этом объекте ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChains`  
 [out] Указатель на адрес `ICorDebugChainEnum` связан объект, который позволяет перечисления всех стека в этом потоке, начиная с цепочке активный (то есть последнее).  
  
## <a name="remarks"></a>Примечания  
 Цепочка стека представляет физический стек вызова для потока. Следующих обстоятельствах создания цепочки границы стека:  
  
- Управляемого и неуправляемого или неуправляемого в управляемый переход.  
  
- Переключение контекста.  
  
- Объект отладчика захват пользовательского потока.  
  
 В простом случае для потока, на котором выполняется только управляемый код в одном контексте однозначное соответствие будет существовать между потоками и цепочек стека.  
  
 Отладчик может потребоваться изменить расположение физических стеков вызова всех потоков в логические стеки вызовов. Будет включать в себя сортировку цепочки всех потоков и их связей "Вызывающий/вызываемый" и перегруппирование.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
