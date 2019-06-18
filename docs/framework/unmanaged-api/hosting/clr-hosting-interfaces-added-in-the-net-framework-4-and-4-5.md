---
title: Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea95789ea1623985a6a53fcf923b70d7df2ad460
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170438"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
В этом разделе описываются интерфейсы, которые неуправляемые узлы можно использовать для интеграции общеязыковой среды выполнения (CLR) в .NET Framework 4, .NET Framework 4.5 и более поздних версий в свои приложения. Эти интерфейсы предоставляют методы для узла, для настройки и загрузки среды выполнения в процесс.  
  
 Все интерфейсы размещения, начиная с .NET Framework 4, имеют следующие характеристики:  
  
- Они используют управление временем существования (`AddRef` и `Release`), инкапсуляцию (неявный контекст) и `QueryInterface` из COM.  
  
- Они не используют COM-типы например `BSTR`, `SAFEARRAY`, или `VARIANT`.  
  
- Отсутствуют модели подразделения, статистической обработки или активации реестра, используйте [функции CoCreateInstance](https://go.microsoft.com/fwlink/?LinkId=142894).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс ICLRAppDomainResourceMonitor](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 Предоставляет методы, которые проверяют домен приложения использование памяти и ЦП.  
  
 [Интерфейс ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 Ведущее приложение может указать диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.  
  
 [Интерфейс ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 Предоставляет [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, который позволяет ведущему приложению задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0 значения больше `DWORD`.  
  
 [Интерфейс ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 Предоставляет методы, возвращающие определенную версию среды CLR, перечислены все установленные среды CLR, все среды выполнения в процессе, возвращающие интерфейс активации и версию среды CLR, используемый для компиляции сборки.  
  
 [Интерфейс ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 Предоставляет [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , предоставляющий интерфейс среды CLR на основании критериев политики, управляемой сборки, версии и файла конфигурации.  
  
 [Интерфейс ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 Предоставляет методы, возвращающие сведения о конкретной среде выполнения, включая версию, каталог и состояние загрузки.  
  
 [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами. Все [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) методы возвращают стандартный COM HRESULT.  
  
 [Интерфейс ICLRStrongName2](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 Предоставляет возможность создания строгих имен, с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов безопасности.  
  
 [Интерфейс ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 Предоставляет все функциональные возможности [интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); Кроме того, предоставляет методы, позволяющие прерывания потоков, задержки в текущем потоке.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Устаревшие интерфейсы размещения CLR и коклассы](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Описание размещения интерфейсы, предоставляемые платформой .NET Framework версий 1.0 и 1.1.  
  
 [Интерфейсы размещения CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 Описание размещения интерфейсы, предоставляемые платформой .NET Framework версии 2.0, 3.0 и 3.5.  
  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 Представляет размещение в .NET Framework.
