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
ms.openlocfilehash: a028d2a8116de4df79f662ee8b2768e6e070428a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141401"
---
# <a name="metahost_policy_flags-enumeration"></a>Перечисление METAHOST_POLICY_FLAGS
Предоставляет политики привязки, которые являются общими для большинства хостов среды выполнения. Это перечисление используется методом [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Определяет политику высокой совместимости, которая не учитывает среду CLR, которая загружается в текущий процесс. Вместо этого он учитывает только установленные CLR и параметры компонента, как производные от самого файла сборки, объявленной встроенной версии или файла конфигурации.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Применяет политику обновления к результату привязки к версии, если точное соответствие не найдено на основе содержимого HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. нетфрамеворк\полици\упградес. Это тот же результат, что и [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Результаты привязки возвращаются, как если бы изображение, предоставленное для вызова, было запущено в новом процессе. В настоящее время `GetRequestedRuntime` игнорирует набор сред выполнения, допускающих загрузку, и привязывает их к набору установленных сред выполнения. Этот флаг позволяет узлу определить, к какой среде выполнения будет привязан EXE-файл при запуске.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Если `GetRequestedRuntime` не удается найти среду выполнения, совместимую с входными параметрами, отображается диалоговое окно ошибка. Начиная с .NET Framework 4,5, это диалоговое окно с сообщением об ошибке может иметь форму диалогового окна компонента Windows, в котором спрашивается, нужно ли пользователю включить соответствующую функцию.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` использует образ процесса (и любой соответствующий файл конфигурации) в качестве дополнительных входных данных для процесса привязки. По умолчанию `GetRequestedRuntime` не попадает в путь к образу процесса (обычно это EXE-файл, который использовался для запуска процесса) при определении среды выполнения для привязки.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` необходимо проверить, установлен ли соответствующий SKU, если в файле конфигурации нет доступных сведений. Это позволяет приложениям, не имеющим файлов конфигурации, корректно завершать работу на более мелких SKU, чем установка по умолчанию .NET Framework. По умолчанию `GetRequestedRuntime` не проверяет, установлен ли соответствующий SKU, если атрибут SKU не указан в элементе `<supportedRuntime />` файла конфигурации.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` следует игнорировать SEM_FAILCRITICALERRORS (который задается вызовом функции [функцию SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) ) и отобразить диалоговое окно ошибки. По умолчанию SEM_FAILCRITICALERRORS подавляет диалоговое окно ошибки. Возможно, он был унаследован от другого процесса, и в вашем сценарии может быть нежелательным сообщение об ошибке.|  
  
## <a name="remarks"></a>Заметки  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [Метод GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
