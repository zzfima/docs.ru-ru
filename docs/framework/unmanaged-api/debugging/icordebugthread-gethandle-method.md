---
title: Метод ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 358597edc9fbc5203e5c00a5fb4d04019281060d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418276"
---
# <a name="icordebugthreadgethandle-method"></a>Метод ICorDebugThread::GetHandle
Возвращает текущий дескриптор для активной части ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `phThreadHandle`  
 [out] Указатель на HTHREAD, который представляет собой дескриптор активной части данного потока.  
  
## <a name="remarks"></a>Примечания  
 Дескриптор может меняться, поскольку процесс выполняется и может быть разным для разных частей потока.  
  
 Этот дескриптор принадлежит API отладки. Отладчик должен его скопировать перед его использованием.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
