---
title: Метод ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140900"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Метод ICLRMetaHost::RequestRuntimeLoadedNotification
Предоставляет функцию обратного вызова, которая гарантированно будет вызываться при первой загрузке версии среды CLR, но еще не запущена. Этот метод заменяет функцию [локкклрверсион](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Параметры  
 `pCallbackFunction`  
 окне Функция обратного вызова, которая вызывается при загрузке новой среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pCallbackFunction` имеет значение null.|  
  
## <a name="remarks"></a>Заметки  
 Обратный вызов работает следующим образом:  
  
- Обратный вызов вызывается, только если среда выполнения загружается в первый раз.  
  
- Обратный вызов не вызывается для повторных загрузок одной и той же среды выполнения.  
  
- Для невходных загрузок среды выполнения вызовы функции обратного вызова сериализуются.  
  
 Функция обратного вызова имеет следующий прототип:  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Прототипы функций обратного вызова имеют следующий вид:  
  
- `pfnCallbackThreadSet`.  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`.  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Если узел намеревается загрузить или вызвать повторную загрузку другой среды выполнения, параметры `pfnCallbackThreadSet` и `pfnCallbackThreadUnset`, предоставляемые функцией обратного вызова, должны использоваться следующим образом:  
  
- `pfnCallbackThreadSet` должен вызываться потоком, который может вызвать загрузку среды выполнения до того, как будет предпринята такая нагрузка.  
  
- `pfnCallbackThreadUnset` должны вызываться, когда поток больше не будет вызывать такую нагрузку во время выполнения (и до возврата из начального обратного вызова).  
  
- `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` не являются недопустимыми.  
  
> [!NOTE]
> Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` вне области действия параметра `pCallbackFunction`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
