---
title: "Метод ICLRMetaHost::RequestRuntimeLoadedNotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7866270d8c9234a375401dfd05b504a06ddbf4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Метод ICLRMetaHost::RequestRuntimeLoadedNotification
Предоставляет функции обратного вызова, которое гарантированно вызывается при первой загрузке версия CLR (CLR), но еще не запущена. Этот метод заменяет [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pCallbackFunction`  
 [in] Функция обратного вызова, который вызывается при загрузке новой среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pCallbackFunction` имеет значение null.|  
  
## <a name="remarks"></a>Примечания  
 Функция обратного вызова работает следующим образом:  
  
-   Обратный вызов выполняется только в том случае, когда среда выполнения загружается в первый раз.  
  
-   Функция обратного вызова не вызывается для реентерабельным загружает ту же среду выполнения.  
  
-   Для загрузки среды выполнения не допускающий повторные входы сериализуются вызовы функции обратного вызова.  
  
 Функция обратного вызова имеет следующий прототип:  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Прототипы функции обратного вызова, следующим образом:  
  
-   `pfnCallbackThreadSet`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   `pfnCallbackThreadUnset`:  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Если узел пытается загрузить или вызывать другой среды выполнения реентерабельным способом `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` параметры, которые указаны в функции обратного вызова необходимо использовать функцию следующим образом:  
  
-   `pfnCallbackThreadSet`должен вызываться потоком, который может вызвать загрузку среды выполнения, до попытки такой загрузки.  
  
-   `pfnCallbackThreadUnset`должен быть вызван, когда поток больше не вызывает загрузку среды выполнения (и до возврата из предыдущего обратного вызова).  
  
-   `pfnCallbackThreadSet`и `pfnCallbackThreadUnset` являются допускает повторные входы.  
  
> [!NOTE]
>  Хост-приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` за пределами области `pCallbackFunction` параметра.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
