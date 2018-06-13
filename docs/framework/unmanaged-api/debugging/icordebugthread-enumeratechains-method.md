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
ms.openlocfilehash: caeb60c33580f7171a6959c3046cf7312868851b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420558"
---
# <a name="icordebugthreadenumeratechains-method"></a>Метод ICorDebugThread::EnumerateChains
Получает указатель на интерфейс ICorDebugChainEnum перечислителя, который содержится в этом объекте ICorDebugThread всех цепочек стека.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppChains`  
 [out] Указатель на адрес `ICorDebugChainEnum` связан объект, который позволяет использовать перечисления стека в этом потоке, начиная с цепочки active (то есть самой последней).  
  
## <a name="remarks"></a>Примечания  
 Цепочка стека представляет физический стек вызова для потока. Следующих обстоятельствах создайте границы цепи стека:  
  
-   Управляемый в неуправляемый или неуправляемый в управляемый переход.  
  
-   Переключение контекста.  
  
-   Значение типа отладчика перехват пользовательского потока.  
  
 В простом случае для потока, на котором выполняется только управляемый код в одном контексте однозначное соответствие будет использоваться между потоками и цепочек стека.  
  
 Отладчик может потребоваться переупорядочивание физических стеков вызова всех потоков в логические стеки вызова. Организуется, сортировка по их связей "Вызывающий/вызываемый" цепочки всех потоков и перегруппирование.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
