---
title: Оптимальные методы сохраняемости
ms.date: 03/30/2017
ms.assetid: 6974c5a4-1af8-4732-ab53-7d694608a3a0
ms.openlocfilehash: 8ffbb3ebfa8f85e2b0052a9df9ada30766accd8e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802522"
---
# <a name="persistence-best-practices"></a>Оптимальные методы сохраняемости
В настоящем документе приведены лучшие методики по проектированию и настройке рабочих процессов, касающиеся сохраняемости рабочих процессов.  
  
## <a name="design-and-implementation-of-durable-workflows"></a>Проектирование и реализация устойчивых рабочих процессов  
 Как правило, рабочие процессы выполняют работу в короткие периоды времени, которые чередуются с промежутками времени, в течение которых рабочие процессы простаивают, ожидая возникновения события. Таким событием может быть сообщение или истечение установки таймера. Чтобы иметь возможность выгрузить экземпляр рабочего процесса, когда он становится простаивающим, узел службы должен сохранить этот экземпляр рабочего процесса. Это возможно, только если экземпляр рабочего процесса не находится в зоне несохраняемости (например, ожидает завершения транзакции или ожидает асинхронный обратный вызов). Для обеспечения выгрузки простаивающего экземпляра рабочего процесса разработчик рабочих процессов должен использовать области транзакций и асинхронные действия только для кратковременных действий. В частности, разработчик должен следить за тем, чтобы действия задержки в пределах этих зон несохраняемости были как можно более кратковременными.  
  
 Сохранение рабочего процесса возможно, только если все типы данных, применяемые в рабочем процессе, являются сериализуемыми. Кроме того, пользовательские типы, используемые в сохраняемых рабочих процессах, должны быть сериализуемыми с помощью <xref:System.Runtime.Serialization.NetDataContractSerializer>, чтобы быть сохраненными в <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
 Экземпляр рабочего процесса не может быть восстановлен в случае сбоя узла или компьютера, если он не был сохранен. Вообще говоря, рекомендуется сохранять экземпляр рабочего процесса в жизненном цикле рабочего процесса как можно раньше.  
  
 Если рабочий процесс занят в течение продолжительного времени, рекомендуется регулярно сохранять экземпляр этого рабочего процесса на протяжении периода его занятости. Это можно обеспечить, добавляя действия <xref:System.Activities.Statements.Persist> по всей последовательности действий, которые поддерживают экземпляр рабочего процесса в состоянии занятости. Благодаря этому очистка памяти в домене приложения, сбои узла или сбои компьютера не вынуждают систему выполнять откат к началу периода занятости. Следует учитывать, что добавление действий <xref:System.Activities.Statements.Persist> к применяемым рабочим процессам приводит к снижению производительности.  
  
 Применение Windows Server App Fabric весьма способствует упрощению настройки и использования сохраняемости. Дополнительные сведения см. в статье [сохраняемость в Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)) .  
  
## <a name="configuration-of-scalability-parameters"></a>Настройка параметров масштабируемости  
 Требования к масштабируемости и производительности определяют значения следующих параметров:  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>  
  
- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A>  
  
 Эти параметры должны быть заданы следующим образом, согласно текущему сценарию.  
  
### <a name="scenario-a-small-number-of-workflow-instances-that-require-optimal-response-time"></a>Сценарий. Небольшое количество экземпляров рабочего процесса, которые требуют оптимального времени ответа  
 В этом сценарии все экземпляры рабочего процесса должны оставаться загруженными, когда они становятся простаивающими. Задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> равным большому значению. Использование этого параметра препятствует перемещению экземпляра рабочего процесса с одного компьютера на другой. Используйте этот параметр, только если соблюдаются одно или несколько из следующих условий.  
  
- Экземпляр рабочего процесса получает единственное сообщение на протяжении всего времени своего существования.  
  
- Все экземпляры рабочего процесса запущены на единственном компьютере  
  
- Все сообщения, полученные экземпляром рабочего процесса, получены одним и тем же компьютером.  
  
 Используйте действия <xref:System.Activities.Statements.Persist> или задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> равным 0, чтобы включить восстановление применяемого экземпляра рабочего процесса после сбоев узла службы или компьютера.  
  
### <a name="scenario-workflow-instances-are-idle-for-long-periods-of-time"></a>Сценарий. Экземпляры рабочего процесса простаивают в течение продолжительных промежутков времени  
 В этом сценарии задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> равным 0, чтобы освобождать ресурсы как можно скорее.  
  
### <a name="scenario-workflow-instances-receive-multiple-messages-in-a-short-period-of-time"></a>Сценарий. Экземпляры рабочих процессов получают множество сообщений за короткий период времени  
 В этом сценарии задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> равным 60 секундам, если эти сообщения получены одним и тем же компьютером. Это предотвращает возникновение быстрой последовательности выгрузок и загрузок экземпляра рабочего процесса. При этом также экземпляр не остается в памяти слишком долго.  
  
 Задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> равным 0 и задайте <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A> равным BasicRetry или AggressiveRetry, если эти сообщения могут быть получены разными компьютерами. Это обеспечивает возможность загрузки экземпляра рабочего процесса другим компьютером.  
  
### <a name="scenario-workflow-uses-delay-activities-with-short-durations"></a>Сценарий. В рабочем процессе используются действия задержки с краткими продолжительностями  
 В этом сценарии <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> регулярно опрашивает базу данных сохраняемости на наличие экземпляров, которые должны быть загружены из-за истечения срока действия <xref:System.Activities.Statements.Delay>. Если <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> находит таймер, установка которого должна истечь в следующем интервале опроса, то хранилище экземпляров рабочих процессов SQL сокращает интервал опроса. Следующий опрос затем произойдет сразу после истечения установки таймера. Таким образом, хранилище экземпляров рабочих процессов SQL достигает высокой точности установок таймеров, которые работают дольше по сравнению с продолжительностью интервала опроса, который задан в <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>. Чтобы обеспечить своевременную обработку более коротких задержек, экземпляр рабочего процесса должен оставаться в памяти в течение по крайней мере одного интервала опроса.  
  
 Задайте <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> равным 0, чтобы записать значение срока действия в базу данных сохраняемости.  
  
 Задайте значение <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> более продолжительным или равным <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, чтобы экземпляр оставался в памяти в течение хотя бы одного интервала опроса.  
  
 Не рекомендуется сокращать значение <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, поскольку это приводит к повышению нагрузки на базу данных сохраняемости. Каждый узел службы, который использует <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, опрашивает базу данных единожды в каждый период обнаружения. Задание <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> равным слишком малому интервалу времени может вызвать снижение производительности системы, если количество узлов службы велико.  
  
## <a name="configuring-the-sql-workflow-instance-store"></a>Настройка хранилища экземпляров рабочих процессов SQL  
 Хранилище экземпляров рабочих процессов SQL имеет следующие параметры конфигурации:  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceEncodingOption%2A>  
 Этот параметр служит для <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> указанием производить сжатие данных о состоянии экземпляра рабочего процесса. Сжатие приводит к уменьшению объема данных, хранящихся в базе данных сохраняемости, и уменьшению сетевого трафика в том случае, если база данных сохраняемости находится на выделенном сервере базы данных. Если используется сжатие, то возникают затраты вычислительных ресурсов на сжатие и извлечение данных о состоянии экземпляра. В большинстве случаев сжатие приводит к повышению производительности.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceCompletionAction%2A>  
 Этот параметр служит для <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> указанием либо оставлять, либо удалять завершенные экземпляры. Хранение завершенных экземпляров становится причиной повышения потребности в памяти для базы данных сохраняемости и приводит к появлению более крупных таблиц, что влечет за собой увеличение затрат времени на поиск в таблицах. Если хранение завершенных экземпляров не требуется для отладки или аудита, то лучше дать указание <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> удалять завершенные экземпляры. Удаленные экземпляры следует хранить, только если пользователь определил процесс их удаления в конечном итоге. Следует учитывать, что ключи корреляции не могут использоваться повторно, пока завершенный экземпляр рабочего процесса находится в хранилище экземпляров.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>  
 Этот параметр определяет максимальный интервал, с которым <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> опрашивает базу данных сохраняемости на наличие экземпляров, которые должны быть загружены по истечении срока действия <xref:System.Activities.Statements.Delay>. Если <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> находит таймер, установка которого истечет в следующем интервале опроса, то сокращает интервал опроса так, чтобы следующий опрос произошел сразу после истечения установки таймера. Благодаря этому в хранилище экземпляров рабочих процессов SQL достигается высокая точность установок таймеров, которые работают дольше, чем <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>.  
  
 Не рекомендуется уменьшать значение <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, поскольку это приводит к повышению нагрузки на базу данных сохраняемости. Каждый узел службы, который использует <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, опрашивает базу данных единожды в каждый период обнаружения. Задание <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> равным слишком малому интервалу может вызвать снижение производительности системы, если количество узлов службы велико.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>  
 Этот параметр определяет интервал, с которым узел возобновляет свою блокировку в базе данных сохраняемости. Сокращение этого интервала позволяет ускорить восстановление экземпляров рабочего процесса в случае сбоя узла или компьютера. С другой стороны, сокращение периода возобновления блокировки приводит к повышению нагрузки на базу данных сохраняемости. Каждый узел службы, который использует <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, обновляет свои блокировки в базе данных единожды за каждый период возобновления. Если на компьютере работает много узлов служб, убедитесь в том, что нагрузка, вызванная возобновлением блокировок, не приводит к снижению производительности системы. Если же происходит снижение, рассмотрите возможность увеличить <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A>  
 Если это включено, то <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> предпринимает повторные попытки загрузки заблокированного экземпляра в течение следующих 30 секунд. Задайте <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> равным BasicRetry или AggressiveRetry, если рабочий процесс получает множество сообщений за короткое время и получение этих сообщений происходит разными компьютерами.  
  
 Таким образом, этот механизм повторения загрузки не порождает издержек производительности, пока не предпринимаются попытки повторения загрузки, поэтому следует всегда включать <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A>.
