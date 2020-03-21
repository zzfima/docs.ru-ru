---
title: Метод ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: 46f047dbec7ff008873540806b76ffe7085086b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178424"
---
# <a name="icorpublishgetprocess-method"></a>Метод ICorPublish::GetProcess
Получает экземпляр [ICorPublishProcess,](icorpublishprocess-interface.md) представляющий процесс с указанным идентификатором.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pid`  
 (в) Идентификатор процесса.  
  
 `ppProcess`  
 (ваут) Указатель на адрес `ICorPublishProcess` экземпляра, представляющего процесс.  
  
## <a name="remarks"></a>Remarks  
 `GetProcess`сбой, если процесс не существует, или не является управляемым процессом, который может быть отдигирован текущим пользователем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorPublish](icorpublish-interface.md)
