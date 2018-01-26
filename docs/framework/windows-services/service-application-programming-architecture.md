---
title: "Программная архитектура приложений служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a>Программная архитектура приложений служб
Приложения служб Windows основаны на класс, наследующий от <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> класса. Переопределите методы этого класса и определить функциональные возможности для их определить поведение службы.  
  
 Ниже перечислены основные классы, используемые при создании службы.  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>— Необходимо переопределить методы <xref:System.ServiceProcess.ServiceBase> класса при создании службы и определить код, чтобы определить, как функциональные возможности службы в этом наследуется класс.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>и <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> — эти классы используются для установки и удаления службы.  
  
 Кроме того, класс с именем <xref:System.ServiceProcess.ServiceController> можно использовать для управления службой. Этот класс не используется при создании службы, но может использоваться для запуска и остановки службы, передавать ей команды и возвращать последовательности перечислений.  
  
## <a name="defining-your-services-behavior"></a>Определение поведения службы  
 В классе службы переопределить функции базового класса, которые определяют, что происходит при изменении состояния службы в диспетчере управления службами. <xref:System.ServiceProcess.ServiceBase> Класс предоставляет следующие методы, которые можно переопределить, чтобы добавить пользовательское поведение.  
  
|Метод|Переопределение позволяет|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Укажите, какие действия должны быть выполнены, при запуске службы. В этой процедуре для службы для выполнения требуемых задач, необходимо написать код.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Указывает, что должно происходить при приостановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Указывает, что должно происходить при остановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Указывает, что должно происходить при возобновлении работы после ее приостановки вашей службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Указывает, что должно происходить непосредственно перед завершением работы, системы, если служба запущена в это время.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Указывает, что должно происходить, когда служба получает пользовательской команды. Дополнительные сведения о пользовательских командах см. в разделе MSDN online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Укажите реакцию службы при получении события управления питанием, например низкого заряда батарей или режима приостановки.|  
  
> [!NOTE]
>  Эти методы соответствуют состояниям, которые служба перемещается по времени существования; Служба переходит из одного состояния к другому. Например, вы никогда не получите службе отвечать на <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> перед тем как <xref:System.ServiceProcess.ServiceBase.OnStart%2A> был вызван.  
  
 Существует несколько других свойств и методов, которые представляют интерес. Сюда входит следующее.  
  
-   <xref:System.ServiceProcess.ServiceBase.Run%2A> Метод <xref:System.ServiceProcess.ServiceBase> класса. Это главная точка входа для службы. При создании службы с помощью шаблона служб Windows, код вставляется в вашем приложении `Main` метод для запуска службы. Этот код выглядит следующим образом:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  В этих примерах используются массивом типа <xref:System.ServiceProcess.ServiceBase>, в который каждой службы, который содержит приложение можно добавить и затем все службы могут выполняться одновременно. Если создается только одна служба, тем не менее, можно не использовать массив, а объявить новый объект, наследуемый от <xref:System.ServiceProcess.ServiceBase> и запустите его. Пример см. в разделе [как: запись службы программным образом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Наборы свойств <xref:System.ServiceProcess.ServiceBase> класса. Они определяют, какие методы могут вызываться в службе. Например, если <xref:System.ServiceProcess.ServiceBase.CanStop%2A> свойству `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> возможность вызова метода в службе. Когда <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> свойству `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> и <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> можно вызывать методы. Если задано одно из этих свойств для `true`, необходимо переопределить и реализовать соответствующий метод.  
  
    > [!NOTE]
    >  Служба должна переопределять по крайней мере <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> для использования.  
  
 Можно также использовать компонент, называемый <xref:System.ServiceProcess.ServiceController> для связи и управлять поведением существующую службу.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
