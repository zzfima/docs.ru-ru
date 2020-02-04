---
title: Указатель функции PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
ms.openlocfilehash: 433f34447d3bd1a57ca1e289cb0eab3facac2c69
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790360"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a>Указатель функции PFN_CLRDataCreateInstance
Указывает на функцию, которая создает объект интерфейса для указанного целевого элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
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
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Глобальные статические функции отладки](debugging-global-static-functions.md)
