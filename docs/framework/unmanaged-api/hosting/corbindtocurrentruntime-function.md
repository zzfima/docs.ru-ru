---
title: Функция CorBindToCurrentRuntime
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0acb322fa3348f0bb2d819529a370110580343c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985885"
---
# <a name="corbindtocurrentruntime-function"></a>Функция CorBindToCurrentRuntime
Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл. Формат XML-файла моделируется стандартного файла конфигурации приложения. Дополнительные сведения о файлах конфигурации см. в разделе [Схема файла конфигурации](../../../../docs/framework/configure-apps/file-schema/index.md).  
  
 Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. См. в разделе [загрузка среда CLR в процесс](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwszFileName`  
 [in] Имя файла конфигурации приложения, который указывает версию среды CLR для загрузки. Если имя файла не указано полное имя, предполагается, что он является в том же каталоге, что и исполняемый файл, вызывающий.  
  
 Версия среды выполнения необходимо загрузить описан в атрибуте версии [ \<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) элемент файла конфигурации.  
  
 Если версия не указана или если `<requiredRuntime>` элемент не найден, загружается последняя версия среды CLR, которая установлена на компьютере.  
  
 `rclsid`  
 [in] `CLSID` Компонентного класса, реализующий [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) или [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс. Поддерживаемые значения: CLSID_CorRuntimeHost или CLSID_CLRRuntimeHost.  
  
 `riid`  
 [in] `IID` Интерфейса, для которого запрашивается. Поддерживаемые значения: IID_ICorRuntimeHost и IID_ICLRRuntimeHost.  
  
 `ppv`  
 [out] Возвращаемый указатель интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [Функция CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [Функция CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [Функция CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [Интерфейс ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [Устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
