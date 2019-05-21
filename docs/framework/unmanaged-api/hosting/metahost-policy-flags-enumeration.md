---
title: Перечисление METAHOST_POLICY_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37a6dc0caa81a365727bfc32a6a0363bb7e1713d
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960145"
---
# <a name="metahostpolicyflags-enumeration"></a>Перечисление METAHOST_POLICY_FLAGS
Предоставляет политики привязки, которые являются общими для большинства сред выполнения. Это перечисление используется с [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод.  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Определяет политику высокой совместимости, которая не учитывает любые общеязыковая среда выполнения (CLR), загруженные в текущий процесс. Вместо этого он считает только установленные среды CLR и настройки компонента, как производный от самого файла сборки, объявленного построения для версии или в файле конфигурации.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Применяет политику обновления к результату bind версии, если точное соответствие не найдено, на основе содержимого HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Это имеет тот же эффект, что [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Привязка результаты возвращаются в том случае, как если бы образа, предоставленного в вызов был запущен в новый процесс. В настоящее время `GetRequestedRuntime` игнорирует набор загружаемых сред выполнения и привязывается к набору установленных сред выполнения. Этот флаг позволяет основному приложению определить, какая среда выполнения, EXE-файла будет привязан к при запуске приложения.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Диалоговое окно ошибки отображается в том случае, если `GetRequestedRuntime` не удается найти среду выполнения, которая совместима с входными параметрами. Начиная с версии [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], это диалоговое окно ошибки может принимать форму в диалоговом окне Windows функция, которая запрашивает, нужна ли пользователь для включения соответствующей функции.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` использует образ процесса (и все соответствующие файлы конфигурации) в качестве дополнительных входных данных для процесса привязки. По умолчанию `GetRequestedRuntime` переключается на путь к образу процесса (как правило, EXE, который использовался для запуска процесса) при определении среды выполнения для привязки.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` необходимо проверить, установлена ли соответствующий номер SKU, если сведения недоступны в файле конфигурации. Это позволяет приложениям, у которых нет файлов конфигурации для корректного завершения сбоем в меньшего размера SKU, чем по умолчанию установка платформы .NET Framework. По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий номер SKU, если атрибут SKU не указан в файле конфигурации `<supportedRuntime />` элемент.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` должен игнорировать SEM_FAILCRITICALERRORS (который устанавливается путем вызова [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) функции) и диалоговое окно ошибки. По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки. Его могут быть унаследованы от другого процесса и автоматической ошибка может быть нежелательно в вашем сценарии.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Metahost.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [Метод GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
