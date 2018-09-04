---
title: Защита служб рабочего процесса
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 28c34ecf7d6d781bfa461b2737cb9325a657f47e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524339"
---
# <a name="securing-workflow-services"></a>Защита служб рабочего процесса
В образце безопасной службы рабочего процесса демонстрируются следующие процедуры.  
  
-   Создание базовой службы рабочего процесса с помощью действий <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>.  
  
-   Использование конфигурации Windows Communication Foundation (WCF) для определения защищенных конечных точек для использования службой рабочего процесса.  
  
-   Создание утверждений внутри настраиваемой политики с использованием <xref:System.ServiceModel.ServiceAuthorizationManager> для проверки утверждений.  
  
## <a name="demonstrates"></a>Демонстрации  
 Использование безопасности WCF для защиты взаимодействия между клиентом и службой рабочего процесса, авторизация на основе утверждений.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце демонстрируется использование инфраструктуры безопасности WCF для защиты службы рабочего процесса, так же, как с помощью стандартной службы WCF. Конкретно, в примере для авторизации используется пользовательское утверждение. В этом случае используется <xref:System.ServiceModel.WSHttpBinding> и безопасность режима сообщений с учетными данными Windows.  
  
 Настраиваемая политика <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) проверяет имя пользователя Windows клиента и анализирует конкретный символ. Если этот символ присутствует, он создает и добавляет утверждение в контекст <xref:System.IdentityModel.Policy.EvaluationContext>. Выполняя это, настраиваемая политика делает утверждение, что клиент имеет этот символ в имени пользователя. Это утверждение может запрашиваться в течение времени существования вызова. Этот символ можно найти в `Constants.cs`.  
  
 Политика авторизации ищет утверждение внутри `SecureWorkFlowAuthZManager`. Если она его находит, она возвращает значение `true` и разрешает продолжение рабочего процесса. В противном случает она возвращает значение `false`, которое вызывает возврат клиенту сообщения «Отказано в доступе». Другие утверждения присутствуют в контексте и могут также проверяться внутри `SecureWorkFlowAuthZManager`.  
  
#### <a name="to-run-this-sample"></a>Запуск образца  
  
1.  Запустите среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с правами администратора.  
  
2.  Загрузка SecuringWorkflowServices.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Для компиляции решения нажмите CTRL+SHIFT+B.  
  
4.  Установите проект Service в качестве проекта для запуска решения.  
  
5.  Чтобы запустить службу без отладки, нажмите клавиши CTRL+F5.  
  
6.  Установите проект Client в качестве проекта для запуска решения.  
  
7.  Чтобы запустить клиент без отладки, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
