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
ms.openlocfilehash: c24963a6e56adfb9f763c6521027744db82cc357
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179365"
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
 (в) Идентификатор интерфейса, который должен быть мгновенно.  
  
 `target`  
 (в) Указатель на реализованный пользователем объект [ICLRDataTarget,](iclrdatatarget-interface.md) представляющий целевой элемент для создания объекта интерфейса.  
  
 `iface`  
 (ваут) Указатель на адрес возвращенного объекта интерфейса.  
  
## <a name="remarks"></a>Remarks  
 Объект `ICLRDataTarget` реализован автором приложения отладки. Реализация зависит от типа представленного целевого элемента. Целевой элемент может быть процесс, свалка памяти, удаленной машины, и так далее.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
