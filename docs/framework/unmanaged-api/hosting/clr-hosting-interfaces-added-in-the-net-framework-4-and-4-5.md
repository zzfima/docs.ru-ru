---
title: "Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65d80734bfbe16c8b5052f8de1e4c6280b663707
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
В этом разделе описываются интерфейсы, которые неуправляемые узлов можно использовать для интеграции общеязыковой среды выполнения (CLR) в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]и более поздних версиях в свои приложения. Эти интерфейсы обеспечивают методы для узла, для настройки и загрузки среды выполнения в процесс.  
  
 Начиная с [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], все размещения интерфейсов имеют следующие характеристики:  
  
-   Используют управление временем существования (`AddRef` и `Release`), инкапсуляцию (неявный контекст) и `QueryInterface` из COM.  
  
-   Они не используют типы COM. Например `BSTR`, `SAFEARRAY`, или `VARIANT`.  
  
-   Отсутствуют модели подразделения, статистической обработки или активации реестра, используйте [функции CoCreateInstance](http://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>Содержание  
 [ICLRAppDomainResourceMonitor-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Предоставляет методы, проверяющие домен приложения использование памяти и ЦП.  
  
 [Iclrdomainmanager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также указать свойства инициализации.  
  
 [ICLRGCManager2-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению установите размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 для значений больше `DWORD`.  
  
 [ICLRMetaHost-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Предоставляет методы, которые возвращают определенную версию среды CLR, список всех установленных сред CLR, все среды выполнения в процессе, возвращающие интерфейс активации и версию среды CLR, который используется для компиляции сборки.  
  
 [Интерфейс ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Предоставляет [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , предоставляющий интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.  
  
 [ICLRRuntimeInfo-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Предоставляет методы, возвращающие сведения о конкретной среде выполнения, включая версию, каталог и состояние загрузки.  
  
 [Iclrstrongname-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Предоставляет базовые глобальные статические функции для подписи сборки со строгими именами. Все [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) методы возвращают стандартные результаты COM HRESULT.  
  
 [Интерфейс ICLRStrongName2](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Предоставляет возможность создавать с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов Secure строгие имена.  
  
 [ICLRTask2-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Предоставляет все функциональные возможности [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Интерфейсы размещения устаревшие CLR и Coclasses](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Описание размещения интерфейсов, предоставляемых в .NET Framework версии 1.0 и 1.1.  
  
 [Интерфейсы размещения CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Описание размещения интерфейсов, предоставляемых в .NET Framework версии 2.0, 3.0 и 3.5.  
  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Представляет размещение в .NET Framework.
