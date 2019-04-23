---
title: Программная архитектура приложений служб
ms.date: 03/30/2017
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
author: ghogen
ms.openlocfilehash: 17e16cec34b381cdfe46e1066c3219a93c3780e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216396"
---
# <a name="service-application-programming-architecture"></a>Программная архитектура приложений служб
В основе приложений-служб Windows лежит класс, наследуемый от класса <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Вы можете переопределить методы из этого класса и определить функции для них, чтобы настроить поведение службы.  
  
 Ниже перечислены основные классы, используемые при создании службы:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> — вы можете переопределить методы из класса <xref:System.ServiceProcess.ServiceBase> при создании службы и определить код, чтобы обозначить функции службы в этом наследуемом классе.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> и <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> — эти классы можно использовать для установки и удаления службы.  
  
 Кроме того, класс с именем <xref:System.ServiceProcess.ServiceController> можно использовать для управления самой службой. Этот класс не используется при создании службы, но может использоваться для ее запуска и остановки, а также передачи команд и возврата последовательностей перечислений.  
  
## <a name="defining-your-services-behavior"></a>Определение поведения службы  
 В классе службы вы можете переопределить функции базового класса, которые определяют, что происходит при изменении состояния службы в диспетчере служб. Класс <xref:System.ServiceProcess.ServiceBase> предоставляет следующие методы, которые можно переопределить, чтобы добавить пользовательское поведение.  
  
|Метод|Переопределение|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Укажите, какие действия должны быть выполнены при запуске службы. В этой процедуре необходимо написать код, чтобы служба выполняла требуемые задачи.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Укажите, что должно происходить при приостановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Укажите, что должно происходить при остановке службы.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Укажите, что должно происходить при возобновлении нормальной работы службы после приостановки.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Укажите, что должно происходить непосредственно перед завершением работы системы, если служба запущена в это время.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Укажите, что должно происходить при получении службой пользовательской команды. Дополнительные сведения о пользовательских командах см. на сайте MSDN.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Укажите, как должна реагировать служба при получении события управления питанием, например низкого заряда батареи или операции приостановки.|  
  
> [!NOTE]
>  Эти методы представляют состояния, через которые служба проходит за время своего существования, а именно — переходы службы от одного состояния к другому. Например, служба будет отвечать на команду <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> только после вызова <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  
  
 Есть несколько других свойств и методов, которые представляют интерес. Сюда входит следующее.  
  
-   Метод <xref:System.ServiceProcess.ServiceBase.Run%2A> в классе <xref:System.ServiceProcess.ServiceBase>. Это главная точка входа для службы. При создании службы с помощью шаблона служб Windows код вставляется в метод `Main` приложения для запуска этой службы. Этот код выглядит так:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  В этих примерах используется массив типа <xref:System.ServiceProcess.ServiceBase>. В него можно добавить каждую службу, которую содержит приложение, а затем запустить все службы одновременно. Если создается только одна служба, вы можете не использовать массив, а просто объявить и запустить новый объект, наследуемый от <xref:System.ServiceProcess.ServiceBase>. Пример см. в статье [Практическое руководство. Создание служб программным способом](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Наборы свойств в классе <xref:System.ServiceProcess.ServiceBase>. Они определяют, какие методы могут вызываться в службе. Например, если свойству <xref:System.ServiceProcess.ServiceBase.CanStop%2A> задать значение `true`, в службе можно вызвать метод <xref:System.ServiceProcess.ServiceBase.OnStop%2A>. Если свойству <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> задать значение `true`, в службе можно вызвать методы <xref:System.ServiceProcess.ServiceBase.OnPause%2A> и <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>. Если одному из этих свойств задать значение `true`, необходимо переопределить и реализовать обработку для соответствующих методов.  
  
    > [!NOTE]
    >  Используемая служба должна переопределять хотя бы <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.  
  
 Можно также использовать компонент, называемый <xref:System.ServiceProcess.ServiceController>, для обмена данными с существующей службой и управления ее поведением.  
  
## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [Практическое руководство. Создание служб Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
