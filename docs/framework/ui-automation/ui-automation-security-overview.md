---
title: Общие сведения о безопасности модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: b35014993f10c3a60c16f784e7dd11b9a20f4f4c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47400599"
---
# <a name="ui-automation-security-overview"></a>Общие сведения о безопасности модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом обзоре описывается модель безопасности для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] в [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)].  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a>контроль учетных записей  
 Безопасность является основным направлением [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] , и среди нововведений можно отметить, что пользователи имеют возможность выполнять запуск от имени обычных пользователей (не администраторов) без обязательной блокировки запуска приложений и служб, которым требуются более высокие привилегии.  
  
 В [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]большинство приложений предоставляется с помощью стандартного или административного токена. Если приложение не идентифицировано как административное приложение, оно запускается в качестве стандартного приложения по умолчанию. Прежде чем приложение, идентифицированное как административное, может быть запущено, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] запрашивает у пользователя разрешение на запуск приложения с повышенными привилегиями. Запрос на продолжение отображается по умолчанию, даже если пользователь является членом локальной группы администраторов, так как администраторы выполняют запуск как обычные пользователи, пока приложение или системный компонент, которому требуются административные учетные данные, не запросит разрешение на запуск.  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a>Задачи, требующие повышенных привилегий  
 Когда пользователь пытается выполнить задачу, для которой требуются административные привилегии, [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] выводит диалоговое окно с запросом на продолжение. Это диалоговое окно защищено от межпроцессного взаимодействия, чтобы вредоносные программы не могли имитировать ввод данных пользователем. Аналогичным образом экран входа в систему обычно недоступен для других процессов.  
  
 Клиенты автоматизации пользовательского интерфейса должны взаимодействовать с другими процессами, а некоторые из них могут запускаться с повышенным уровнем привилегий. Клиентам также может требоваться доступ к диалоговым окнам системы, которые обычно невидимы для других процессов. Таким образом, клиенты [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны быть доверенными для системы и должны запускаться со специальными привилегиями.  
  
 Чтобы быть доверенными для взаимодействия с приложениями, работающими на более высоком уровне привилегий, приложения должны быть подписаны.  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a>Файлы манифеста  
 Для получения доступа к защищенному системой [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]приложения должны быть построены с файлом манифеста, включающим специальный атрибут. Этот атрибут `uiAccess` включен в тег `requestedExecutionLevel` , как показано ниже:  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 Значение атрибута `level` в этом коде приводится только для примера.  
  
 `UIAccess` имеет значение false по умолчанию; это означает, что если этот атрибут не указан или если отсутствует манифест сборки, приложение не сможет получить доступ к защищенному [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
 Дополнительные сведения о [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] безопасности, подписи приложений и при создании манифестов сборки см. в разделе «Developer лучшие методики и рекомендации для приложений в среде с минимальными привилегиями» на [MSDN](https://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp).
