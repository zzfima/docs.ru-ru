---
title: Руководство по миграции
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e04c63754960dca44558d888b8ce357220562ea7
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="migration-guidance"></a>Руководство по миграции
В составе [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] корпорация Майкрософт выпускает вторую основную версию [!INCLUDE[wf](../../../includes/wf-md.md)]. [!INCLUDE[wf1](../../../includes/wf1-md.md)] была выпущена в составе [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (она включала типы в пространствах имен System.Workflow.*, которые теперь называются WF3) и улучшена в [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. WF3 также является частью [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], но он сосуществует с новой технологией рабочего процесса (типы в System.Activities.\* пространств имен; называются WF4). При принятии решения об использовании WF4 важно помнить, что управление временем осуществляет пользователь.  
  
-   WF3 представляет собой полностью поддерживаемую часть [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
-   Приложения WF3 запускаются в [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] без внесения изменений, при этом они по-прежнему полностью поддерживаются.  
  
-   Могут создаваться новые приложения WF3, а существующие приложения можно изменить в [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], при этом они полностью поддерживаются.  
  
 Таким образом, решение об использовании .NET Framework 4 связано с решением о переходе на WF4 (System.Activities.*) с WF3 (System.Workflow.\*). В этом разделе приведены ссылки на руководство по миграции в WF, в котором описывается работа с WF3 и WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Техническая документация и рецепты по миграции WF.  
 [Общие сведения о миграции WF](http://go.microsoft.com/fwlink/?LinkId=153873) разделе представлен подробный обзор связи между стратегиями миграции WF3 и WF4. В сопутствующих разделах описываются следующие темы.  
  
 [Общие сведения о миграции WF](http://go.microsoft.com/fwlink/?LinkId=153873)  
 Описывает связи между WF3 и WF4, а также новые возможности пользователей технологии рабочих процессов в .NET 4.  
  
 [Миграция WF: Рекомендации по разработке WF3](http://go.microsoft.com/fwlink/?LinkId=153852)  
 Описывается разработка артефактов WF3 с учетом возможностей упрощения миграции на WF4.  
  
 [Руководство по WF: правила](http://go.microsoft.com/fwlink/?LinkId=153854)  
 Описывает методы внедрения технологий, основанных на правилах, в решения [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
 [Руководство по WF: Конечный автомат](http://go.microsoft.com/fwlink/?LinkId=153855)  
 Описывает моделирование потока управления WF4 при отсутствии действия конечного автомата.  
  
 Обратите внимание, что это руководство относится только к проектам рабочих процессов, использующих платформу .NET Framework 4. Рабочие процессы конечного автомата были добавлены в .NET 4.0.1 с выпуском обновления платформы версии 1 и являлись частью платформы .NET Framework 4.5. [!INCLUDE[crabout](../../../includes/crabout-md.md)] рабочие процессы в .NET 4.0.1 - 4.0.3 и .NET Framework 4.5 см. в разделе [обновление 4.0.1 компоненты Microsoft .NET Framework 4](http://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) и [конечных автоматов](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).  
  
 [Миграции WF: Настраиваемые действия](http://go.microsoft.com/fwlink/?LinkId=153856)  
 Обеспечивает примеры и инструкции по изменению структуры настраиваемых действий WF3 в WF4.  
  
 [Справочник по миграции WF: Расширенные настраиваемые действия](http://go.microsoft.com/fwlink/?LinkId=275560)  
 Предоставляет рекомендации по перепроектированию расширенных пользовательских действий WF3, использующих очереди WF3 и планирование дочерних действий в виде пользовательских действий WF4.  
  
 [Справочник по миграции WF: рабочие процессы](http://go.microsoft.com/fwlink/?LinkId=153858)  
 Обеспечивает примеры и инструкции по изменению структуры рабочих процессов WF3 в WF4.  
  
 [Миграция WF: Размещение рабочих процессов](http://go.microsoft.com/fwlink/?LinkId=275561)  
 Предоставляет рекомендации по перепроектированию кода размещения WF3 как кода размещения для WF4. Цель - описать ключевые различия процессов размещения рабочего процесса в WF3 и WF4.  
  
 [Миграции WF: Отслеживание рабочего процесса](http://go.microsoft.com/fwlink/?LinkId=275562)  
 Предоставляет рекомендации по перепроектированию кода отслеживания и конфигурации WF3 при помощи эквивалентного кода отслеживания и конфигурации для WF4.  
  
 [Руководство по WF: Службы рабочих процессов](http://go.microsoft.com/fwlink/?LinkId=275564)  
 Предоставляет построенные на примерах пошаговые инструкции по перепроектированию часто используемых рабочих процессов, которые реализуют веб-службы Windows Communication Foundation (WCF) (называемые службами рабочих процессов), созданные в WF3, для использования средств WF4.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Statements.Interop>
