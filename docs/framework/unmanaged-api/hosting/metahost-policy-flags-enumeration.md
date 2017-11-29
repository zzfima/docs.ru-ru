---
title: "Перечисление METAHOST_POLICY_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_POLICY_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_POLICY_FLAGS
helpviewer_keywords: METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8946fdcc7c23e11a3f3d78070532ac0bf72b33b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="metahostpolicyflags-enumeration"></a>Перечисление METAHOST_POLICY_FLAGS
Предоставляет политики привязки, которые являются общими для большинства сред выполнения. Это перечисление используется методом [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Определяет политику высокой совместимости, которая не учитывает любые общеязыковая среда выполнения (CLR), который загружается текущего процесса. Вместо этого она рассматривает только установленные среды CLR и предпочтения компонента, как производный от самого файла сборки, объявленного построения для версии или в файле конфигурации.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Применяет политику обновления результат привязки версии, если точное соответствие не найдено, на основе содержимого реестр\\. NETFramework\Policy\Upgrades. Это действует так же, как [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Результаты привязки возвращаются, как если бы было запущено образа, предоставленного для вызова метода в новом процессе. В настоящее время `GetRequestedRuntime` игнорирует набор загружаемых сред выполнения и привязывается к набору установленных исполняющих сред. Этот флаг позволяет основному приложению определить, какие среда выполнения будет привязан EXE-файла при его запуске.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Если откроется диалоговое окно ошибки `GetRequestedRuntime` не удается найти среду выполнения, которая совместима со входными параметрами. Начиная с версии [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], это диалоговое окно ошибки могут принимать форму Windows функция диалогового окна, запрашивает, нужна ли пользователь включить соответствующую функцию.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime`использует в качестве дополнительных входных данных для процесса привязки образ процесса (и все соответствующие файлы конфигурации). По умолчанию `GetRequestedRuntime` не применяли пути образа процесса (как правило, EXE, который использовался для запуска процесса) при определении среды выполнения для привязки.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`необходимо проверить, установлен ли соответствующий SKU при сведения недоступны в файле конфигурации. Это позволяет приложениям, не имеющих файлы конфигурации для корректного сбоя в SKU меньше, чем по умолчанию установка платформы .NET Framework. По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемента.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`необходимо проверить, установлен ли соответствующий SKU при сведения недоступны в файле конфигурации. Это позволяет приложениям, не имеющих файлы конфигурации для корректного сбоя в SKU меньше, чем по умолчанию установка платформы .NET Framework. По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемента.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime`следует игнорировать SEM_FAILCRITICALERRORS (который устанавливается путем вызова [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) функции) и Показать диалоговое окно ошибки. По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки. Он может быть унаследованы от другого процесса и автоматической ошибки может быть нежелательно в сценарий.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Metahost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [GetRequestedRuntime-метод](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
