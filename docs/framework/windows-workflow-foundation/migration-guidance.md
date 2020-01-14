---
title: Руководство по миграции
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: f0c21d32b745a51bada9133230dd0c87be9c915e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937968"
---
# <a name="migration-guidance"></a>Руководство по миграции

В .NET Framework 4 корпорация Майкрософт выпускает вторую основную версию Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] была выпущена в WinFX (Это включало типы в пространствах имен System. Workflow.\*, теперь называется WF3) и улучшено в .NET Framework 3,5. WF3 также является частью .NET Framework 4, но она существует вместе с новой технологией рабочих процессов (типы в пространствах имен System. Activitys.\*, называемые WF4). При принятии решения об использовании WF4 важно помнить, что управление временем осуществляет пользователь.  
  
- WF3 является полностью поддерживаемой частью .NET Framework 4.  
  
- Приложения WF3 выполняются на .NET Framework 4 без изменений и продолжают поддерживаться полностью.  
  
- Можно создавать новые приложения WF3, а существующие приложения можно редактировать в Visual Studio 2012 и полностью поддерживаются.  
  
 Таким решением, решение об принятии .NET Framework 4 отделено от вашего решения о переходе на WF4 (System. Activity.\*) из WF3 (System. Workflow.\*). В этом разделе приведены ссылки на руководство по миграции в WF, в котором описывается работа с WF3 и WF4.  
  
## <a name="wf-migration-white-papers-and-cookbooks"></a>Технические документы и справочники по переносу WF

 В разделе [Обзор миграции WF](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)) представлен общий обзор отношений между WF3 и WF4 и стратегиями миграции. В сопутствующих разделах описываются следующие темы.  
  
 [Общие сведения о миграции WF](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Описывает связи между WF3 и WF4, а также новые возможности пользователей технологии рабочих процессов в .NET 4.  
  
 [Миграция WF. рекомендации по разработке WF3](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Описывается разработка артефактов WF3 с учетом возможностей упрощения миграции на WF4.  
  
 [Руководство по WF: правила](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Описывает, как перенести связанные с правилами инвестиции в решения .NET Framework 4.  
  
 [Руководство по WF: конечный автомат](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Описывает моделирование потока управления WF4 при отсутствии действия конечного автомата.  
  
 Обратите внимание, что это руководство относится только к проектам рабочих процессов, использующих платформу .NET Framework 4. Рабочие процессы конечного автомата были добавлены в .NET 4.0.1 с выпуском обновления платформы версии 1 и являлись частью платформы .NET Framework 4.5. Дополнительные сведения о рабочих процессах конечного автомата в .NET 4.0.1-4.0.3 и .NET Framework 4,5 см. в разделе [Обновление 4.0.1 для функций Microsoft .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) и [рабочих процессов конечного автомата](state-machine-workflows.md).  
  
 [Cookbook миграции WF. пользовательские действия](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Обеспечивает примеры и инструкции по изменению структуры настраиваемых действий WF3 в WF4.  
  
 [Cookbook миграции WF. Расширенные пользовательские действия](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Предоставляет рекомендации по перепроектированию расширенных пользовательских действий WF3, использующих очереди WF3 и планирование дочерних действий в виде пользовательских действий WF4.  
  
 [Cookbook миграции WF. рабочие процессы](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Обеспечивает примеры и инструкции по изменению структуры рабочих процессов WF3 в WF4.  
  
 [Cookbook миграции WF. размещение рабочих процессов](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Предоставляет рекомендации по перепроектированию кода размещения WF3 как кода размещения для WF4. Цель - описать ключевые различия процессов размещения рабочего процесса в WF3 и WF4.  
  
 [Cookbook миграции WF. Отслеживание рабочих процессов](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Предоставляет рекомендации по перепроектированию кода отслеживания и конфигурации WF3 при помощи эквивалентного кода отслеживания и конфигурации для WF4.  
  
 [Руководство по WF. службы рабочих процессов](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Предоставляет построенные на примерах пошаговые инструкции по перепроектированию часто используемых рабочих процессов, которые реализуют веб-службы Windows Communication Foundation (WCF) (называемые службами рабочих процессов), созданные в WF3, для использования средств WF4.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Activities.Statements.Interop>
