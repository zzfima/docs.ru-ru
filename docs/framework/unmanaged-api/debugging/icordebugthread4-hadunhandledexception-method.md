---
title: Метод ICorDebugThread4::HadUnhandledException
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12433786f353212c1ffbd57e9bf526c3ecc60e9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163635"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>Метод ICorDebugThread4::HadUnhandledException
Указывает, возникало ли когда-либо поток необработанное исключение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Параметры  
 `ppBlockingObjectEnum`  
 [out] Указатель на адрес, упорядоченный перечисления [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Поток был необработанное исключение с момента его создания.|  
|S_FALSE|Поток никогда не устанавливался необработанное исключение.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод указывает, возникало ли когда-либо поток необработанное исключение. К моменту запущен обратный вызов необработанного исключения или собственного JIT-присоединением инициируется, этот метод гарантированно возвращает S_OK. Нет никакой гарантии, [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) метод возвращает необработанное исключение; тем не менее, он будет, если процесс не еще продолжается после получения обратного вызова необработанного исключения или при собственного JIT-присоединения. Кроме того можно (хотя и маловероятно) иметь более одного потока с необработанное исключение во время активации собственного JIT-присоединением. В этом случае нет способа определить, какое исключение инициировало JIT-присоединением.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
