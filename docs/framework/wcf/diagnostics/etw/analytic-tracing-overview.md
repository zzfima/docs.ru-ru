---
title: "Общие сведения об аналитическом отслеживании"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2dd456401073d8c7f3c7bc9fbfbe5c11dbbd4e58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="analytic-tracing-overview"></a>Общие сведения об аналитическом отслеживании
Аналитическая трассировка платформы [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] - это набор высокопроизводительных функций с низкой детализацией, добавляемый к трассировке событий Windows (ETW). Трассировка событий Windows работает на уровне ядра, что значительно снижает издержки операций трассировки. Она эффективно буферизует события режима пользователя и ядра и позволяет динамически включать ведение журнала, при этом не требуется перезагружать службу. После их создания и получения данные трассировки отображаются в журналах событий.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] трассировке событий Windows см. в разделе [Усовершенствованная отладка и настройка производительности с помощью приложения ETW](http://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Помимо использования журналов событий Windows, безопасности и приложений для анализа приложения, в [!INCLUDE[wv](../../../../../includes/wv-md.md)] и [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] появились дополнительные «Журналы приложений» и «Журналы служб». Эти новые журналы предназначены для сохранения событий для конкретного приложения или для конкретного компонента, а не глобальных событий, имеющих глобальные последствия для системы (как, например, события в журнале безопасности). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] объединяет и коррелирует запись событий трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] , журналов сообщений [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и записей отслеживания [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] в журналы приложений и служб.  
  
## <a name="concepts-and-capabilities"></a>Основные понятия и возможности  
 Основные понятия и возможности аналитической трассировки [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] .  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Включение параметров диагностики WCF  
 Диагностика WCF включается в \<system.serviceModel >\<диагностики > раздела конфигурации.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 Параметры диагностики WCF для виртуального приложения служб IIS, размещенного на веб-сервере, настраиваются в его файле Web.config. Также можно создать файл Web.config во вложенном каталоге приложения.  При этом параметры будут применены ко всем службам во вложенном каталоге.  Чтобы обеспечить инициализацию параметров диагностики для всех служб приложения, параметры должны находиться в файле Web.config, расположенном в каталоге приложения, а не в одном из вложенных каталогов.  
  
### <a name="channels"></a>Каналы  
 Приложение ETW позволяет программным компонентам направлять события трассировки определенной аудитории при помощь каналов. Например, события для системных администраторов можно отправлять в один канал, а события, которые интересны разработчикам приложений, - в другой. Каналы именуются и регистрируются в Windows, чтобы потребители могли просматривать события из определенного канала с помощью средства просмотра событий.  
  
 Функция аналитической трассировки платформы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] для [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] производит запись в канал Microsoft-Windows-Application-Server-Applications. Этот канал специально предназначен для тех пользователей, которым требуется наблюдать за состоянием работающих служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] . Он определяет небольшой набор событий, который можно использовать для широкого круга задач по наблюдению за состоянием и устранению неполадок.  
  
 Чтобы включить использование файла манифеста средства отслеживания событий для Windows для обеспечения правильной расшифровки сообщений в журнале событий, воспользуйтесь программой командной строки ServiceModelReg следующим образом:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Динамическая конфигурация  
 С помощью инфраструктуры ETW трассировку можно включать и настраивать динамически, используя стандартные средства Windows. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Dynamically Enabling Analytic Tracing](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Трассировка потока сообщений  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] том, как включить трассировку потока сообщений, см. в разделе [Configuring Message Flow Tracing](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Ключевые слова  
 Ключевые слова используются, чтобы фильтровать сообщения трассировки и определять, какой компонент [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] создал данное событие. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Dynamically Enabling Analytic Tracing](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).
