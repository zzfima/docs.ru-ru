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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089774"
---
# <a name="clrdatacreateinstance-function"></a>Функция CLRDataCreateInstance
Создает объект интерфейса для заданного целевого элемента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор интерфейса для создания экземпляра.  
  
 `target`  
 [in] Указатель на реализуется пользователем [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) , представляющий целевой элемент, для которого создается объект интерфейса.  
  
 `iface`  
 [out] Указатель на адрес объекта возвращенный интерфейс.  
  
## <a name="remarks"></a>Примечания  
 `ICLRDataTarget` Объект реализуется разработчиком отладки приложения. Реализация зависит от тип представляемого целевого элемента. Конечный элемент может быть процесс, дамп памяти, удаленный компьютер и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
