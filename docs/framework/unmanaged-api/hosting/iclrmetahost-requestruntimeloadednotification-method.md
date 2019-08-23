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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 539f69c33b67ad1a8a514062c5d777deaced1599
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965003"
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
  
## <a name="remarks"></a>Примечания  
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
  
- `pfnCallbackThreadSet`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Если узел намеревается загрузить или вызвать повторную загрузку другой среды выполнения, `pfnCallbackThreadSet` параметры и `pfnCallbackThreadUnset` , предоставленные в функции обратного вызова, должны использоваться следующим образом:  
  
- `pfnCallbackThreadSet`должен вызываться потоком, который может вызвать загрузку среды выполнения до того, как будет предпринята такая нагрузка.  
  
- `pfnCallbackThreadUnset`должен вызываться, когда поток больше не будет вызывать такую нагрузку во время выполнения (и до возврата из начального обратного вызова).  
  
- `pfnCallbackThreadSet`и `pfnCallbackThreadUnset` не являются недопустимыми для повторного входа.  
  
> [!NOTE]
> Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` `pCallbackFunction` вне области действия параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Метахост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
