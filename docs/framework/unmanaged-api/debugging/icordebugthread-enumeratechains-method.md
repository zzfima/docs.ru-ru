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
ms.openlocfilehash: 38fe50f5a6608bb27d7a7818dee4784a7f8113ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133607"
---
# <a name="icordebugthreadenumeratechains-method"></a>Метод ICorDebugThread::EnumerateChains
Получает указатель интерфейса на перечислитель Икордебугчаиненум, который содержит все цепочки стека в этом объекте ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppChains`  
 заполняет Указатель на адрес объекта `ICorDebugChainEnum`, который позволяет перечислить все цепочки стека в этом потоке, начиная с активной (то есть самой последней) цепочки.  
  
## <a name="remarks"></a>Заметки  
 Цепочка стека представляет физический стек вызовов для потока. В следующих случаях создается граница цепочки стеков:  
  
- Переход с управляемого на неуправляемый или неуправляемый на управляемый.  
  
- Переключение контекста.  
  
- Перехват пользовательского потока отладчиком.  
  
 В простом случае для потока, в котором выполняется исключительно управляемый код в одном контексте, между потоками и цепочками стеков будет существовать соответствие "один к одному".  
  
 Отладчик может захотеть перераспределить физические стеки вызовов всех потоков на логические стеки вызовов. Это может привести к сортировке всех цепочек потоков по связям "Вызывающий/вызываемый" и их перегруппировку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
