---
title: "Метод ICorDebugThread::EnumerateChains"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.EnumerateChains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67b5a5da0a0053536ab4331e9d134464a4330500
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
