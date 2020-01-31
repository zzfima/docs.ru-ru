---
title: Метод ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 5f785b22a3fbda6403c124ec70757b16f5335907
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790759"
---
# <a name="icorpublishenumprocesses-method"></a>Метод ICorPublish::EnumProcesses
Возвращает перечислитель для управляемых процессов, выполняющихся на этом компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Type`  
 Значение перечисления [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) , указывающее тип получаемого процесса. В текущей версии допускается только COR_PUB_MANAGEDONLY.  
  
 `ppIEnum`  
 Указатель на адрес экземпляра [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , который является перечислителем процессов.  
  
## <a name="remarks"></a>Заметки  
 Коллекция процессов перечислителя основана на моментальном снимке процессов, выполняемых при вызове метода `EnumProcesses`. Перечислитель не будет включать процессы, которые завершаются до или после вызова `EnumProcesses`.  
  
 Метод `EnumProcesses` может быть вызван более одного раза в этом экземпляре [ICorPublish](icorpublish-interface.md) для создания новой актуальной коллекции процессов. Последующие вызовы метода `EnumProcesses` не будут затронуты существующими коллекциями.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorPublish](icorpublish-interface.md)
