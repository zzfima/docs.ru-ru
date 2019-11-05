---
title: Функция CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: 71836108dbd0ce01a64b4d9ac773c28d385dfd7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099678"
---
# <a name="clrdatacreateinstance-function"></a>Функция CLRDataCreateInstance
Создает объект интерфейса для указанного целевого элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iid`  
 окне Идентификатор интерфейса, для которого создается экземпляр.  
  
 `target`  
 окне Указатель на реализуемый пользователем объект [ICLRDataTarget](iclrdatatarget-interface.md) , представляющий целевой элемент, для которого создается объект интерфейса.  
  
 `iface`  
 заполняет Указатель на адрес возвращенного объекта интерфейса.  
  
## <a name="remarks"></a>Заметки  
 Объект `ICLRDataTarget` реализуется модулем записи приложения отладки. Реализация зависит от типа представляемого целевого элемента. Целевой элемент может быть процессом, дампом памяти, удаленным компьютером и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
