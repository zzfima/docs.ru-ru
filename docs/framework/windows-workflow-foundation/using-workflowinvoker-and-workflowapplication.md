---
title: Использование WorkflowInvoker и WorkflowApplication
ms.date: 03/30/2017
ms.assetid: cd0e583c-a3f9-4fa2-b247-c7b3368c48a7
ms.openlocfilehash: 5d09fc3c902b1993b32edf3e9f92393433281636
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182706"
---
# <a name="using-workflowinvoker-and-workflowapplication"></a>Использование WorkflowInvoker и WorkflowApplication
Фонд рабочего процесса Windows (WF) предоставляет несколько методов хостинга рабочих процессов. <xref:System.Activities.WorkflowInvoker> предоставляет простой способ вызова рабочего процесса аналогично вызову метода и может использоваться только для рабочих процессов, не использующих сохраняемость. <xref:System.Activities.WorkflowApplication> предоставляет улучшенную модель выполнения рабочих процессов, которая обеспечивает уведомления о событиях жизненного цикла, управление выполнением, возобновление закладок и сохраняемость. <xref:System.ServiceModel.Activities.WorkflowServiceHost> предоставляет поддержку для действий по обмену сообщениями и главным образом используется со службами Workflow Service. В этом разделе вы познакомитесь с размещением рабочих процессов в <xref:System.Activities.WorkflowInvoker> и <xref:System.Activities.WorkflowApplication>. Для получения дополнительной информации <xref:System.ServiceModel.Activities.WorkflowServiceHost>о работе хостинга с, см. [Службы обработки рабочего процесса](../wcf/feature-details/workflow-services.md) и [хостинг служб ы работы Обзор](../wcf/feature-details/hosting-workflow-services-overview.md).  
  
## <a name="using-workflowinvoker"></a>Использование WorkflowInvoker  
 <xref:System.Activities.WorkflowInvoker> предоставляет модель для исполнения рабочего процесса аналогично вызову метода. Чтобы вызвать рабочий процесс при помощи <xref:System.Activities.WorkflowInvoker>, вызовите метод <xref:System.Activities.WorkflowInvoker.Invoke%2A> и передайте определение вызываемого рабочего процесса. В данном примере действие <xref:System.Activities.Statements.WriteLine> вызывается при помощи <xref:System.Activities.WorkflowInvoker>.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#1)]  
  
 Если рабочий процесс вызывается при помощи <xref:System.Activities.WorkflowInvoker>, рабочий процесс исполняется в вызывающем потоке и метод <xref:System.Activities.WorkflowInvoker.Invoke%2A> блокируется до завершения рабочего процесса, включая период неактивности. Чтобы задать интервал ожидания, в течение которого рабочий процесс должен завершиться, используйте одну из перегруженных версий метода <xref:System.Activities.WorkflowInvoker.Invoke%2A>, принимающую параметр <xref:System.TimeSpan>. В данном примере рабочий процесс вызывается дважды с использованием двух разных интервалов ожидания. Первый рабочий процесс завершается, а второй не завершается.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#50)]  
  
> [!NOTE]
> Исключение <xref:System.TimeoutException> создается только в случае, если время ожидания истекло и рабочий процесс перешел в состояние бездействия во время выполнения. Рабочий процесс, не завершающийся в течение отведенного времени ожидания, завершается успешно, если не переходит в состояние простоя.  
  
 <xref:System.Activities.WorkflowInvoker> предоставляет также асинхронные версии метода вызова. Дополнительные сведения см. в разделе <xref:System.Activities.WorkflowInvoker.InvokeAsync%2A> и <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>.  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Настройка входных аргументов рабочего процесса  
 Данные можно передать в рабочий процесс при помощи словаря входных параметров, ключом которого является имя аргумента, сопоставляемого с входными аргументами рабочего процесса. В данном примере вызывается действие <xref:System.Activities.Statements.WriteLine>, а значение его аргумента <xref:System.Activities.Statements.WriteLine.Text%2A> указывается при помощи словаря входных параметров.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#3)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Получение выходных аргументов рабочего процесса  
 Выходные параметры рабочего процесса можно получить при помощи словаря выходов, возвращаемого из вызова <xref:System.Activities.WorkflowInvoker.Invoke%2A>. В следующем примере вызывается рабочий процесс, состоящий из одного действия `Divide`, которое имеет два входных аргумента и два выходных аргумента. При вызове рабочего процесса передается словарь `arguments`, содержащий значения каждого входного аргумента с указанием имени аргумента. После завершения вызова `Invoke` в словаре выходных данных `outputs` возвращается каждый выходной аргумент с указанием имени.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#120](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#120)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#20](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#20)]  
  
 Для рабочего процесса, производного от <xref:System.Activities.ActivityWithResult>, такого как `CodeActivity<TResult>` или `Activity<TResult>`, если имеются выходные аргументы, помимо правильно определенного выходного аргумента <xref:System.Activities.Activity%601.Result%2A>, для получения дополнительных аргументов необходимо использовать неуниверсальную перегруженную версию `Invoke`. Для этого определение рабочего процесса, переданное в `Invoke`, должно быть типа <xref:System.Activities.Activity>. В этом примере действие `Divide` является производным от `CodeActivity<int>`, но объявляется как <xref:System.Activities.Activity>, поэтому используется неуниверсальная перегруженная версия `Invoke`, которая возвращает словарь аргументов вместо одиночного значения.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#121](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#121)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#21)]  
  
## <a name="using-workflowapplication"></a>Использование WorkflowApplication  
 <xref:System.Activities.WorkflowApplication> предоставляет широкий набор возможностей для управления экземплярами рабочего процесса. <xref:System.Activities.WorkflowApplication> действует как потокобезопасный прокси-сервер для настоящего <xref:System.Activities.Hosting.WorkflowInstance>, инкапсулирующего среду выполнения и предоставляющего методы для создания и загрузки экземпляров рабочего процесса, приостановки и возобновления, прекращения и уведомления о событиях жизненного цикла. Чтобы запустить рабочий процесс при помощи <xref:System.Activities.WorkflowApplication>, создайте <xref:System.Activities.WorkflowApplication>, подпишитесь на любые желаемые события жизненного цикла, начните рабочий процесс и дождитесь его завершения. В данном примере создается определение рабочего процесса, состоящее из действия <xref:System.Activities.Statements.WriteLine>, и <xref:System.Activities.WorkflowApplication> с помощью указанного определения рабочего процесса. <xref:System.Activities.WorkflowApplication.Completed%2A> обрабатывается, чтобы узел получил уведомление о завершении рабочего процесса. Рабочий процесс начался вызовом <xref:System.Activities.WorkflowApplication.Run%2A>, и узел ожидает завершения рабочего процесса. После завершения рабочего процесса задается <xref:System.Threading.AutoResetEvent> и ведущее приложение может возобновить выполнение, как показано в следующем примере.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#31](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#31)]  
  
### <a name="workflowapplication-lifecycle-events"></a>События жизненного цикла WorkflowApplication  
 В дополнение к <xref:System.Activities.WorkflowApplication.Completed%2A> авторы узла могут получать уведомление, когда рабочий процесс выгружается (<xref:System.Activities.WorkflowApplication.Unloaded%2A>), прекращается (<xref:System.Activities.WorkflowApplication.Aborted%2A>), переходит в состояние бездействия (<xref:System.Activities.WorkflowApplication.Idle%2A> и <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>) или когда происходит необработанное исключение (<xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>). Разработчики приложения рабочего процесса могут обработать эти уведомления и предпринять надлежащие меры, как показано в следующем примере.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#32](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#32)]  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Настройка входных аргументов рабочего процесса  
 Данные могут передаваться в рабочий процесс в его начале при помощи словаря параметров, подобно тому, как данные передаются при помощи <xref:System.Activities.WorkflowInvoker>. Каждый элемент в словаре сопоставляется с входным аргументом указанного рабочего процесса. В данном примере вызывается рабочий процесс, состоящий из действия <xref:System.Activities.Statements.WriteLine>, и его аргумент <xref:System.Activities.Statements.WriteLine.Text%2A> указывается при помощи словаря входных параметров.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#30](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#30)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Получение выходных аргументов рабочего процесса  
 После завершения рабочего процесса любой из выходных аргументов можно извлечь в обработчик <xref:System.Activities.WorkflowApplication.Completed%2A>, обратившись к словарю <xref:System.Activities.WorkflowApplicationCompletedEventArgs.Outputs%2A?displayProperty=nameWithType>. В следующем примере рабочий процесс размещается с помощью <xref:System.Activities.WorkflowApplication>. Экземпляр <xref:System.Activities.WorkflowApplication> построен с использованием определения рабочего процесса, состоящего из одного `DiceRoll` действия. Действие `DiceRoll` имеет два выходных аргумента, представляющих результаты броска игральных костей. После завершения рабочего процесса выходные параметры возвращаются из обработчика <xref:System.Activities.WorkflowApplication.Completed%2A>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#130](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#130)]  
  
 [!code-csharp[CFX_WorkflowApplicationExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#21)]  
  
> [!NOTE]
> <xref:System.Activities.WorkflowApplication> и <xref:System.Activities.WorkflowInvoker> получают словарь входных аргументов и возвращают словарь аргументов `out`. Эти параметры словаря, свойства и возвращаемые значения имеют тип `IDictionary<string, object>`. Фактически передаваемым экземпляром класса словаря может быть любой класс, который реализует `IDictionary<string, object>`. В этих примерах используется `Dictionary<string, object>`. Для получения дополнительной информации <xref:System.Collections.Generic.IDictionary%602> <xref:System.Collections.Generic.Dictionary%602>о словарях, см.  
  
### <a name="passing-data-into-a-running-workflow-using-bookmarks"></a>Передача данных в запущенный рабочий процесс при помощи закладок  
 Закладки - это механизм, при помощи которого действие может пассивно ждать возобновления; с их помощью можно передавать данные в запущенный экземпляр рабочего процесса. Если действие ждет данные, оно может создать <xref:System.Activities.Bookmark> и зарегистрировать метод обратного вызова, который будет вызываться, когда возобновляется <xref:System.Activities.Bookmark>, как показано в следующем примере.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
 При выполнении действие `ReadLine` создает <xref:System.Activities.Bookmark>, регистрирует обратный вызов и ждет возобновления чтения с закладки <xref:System.Activities.Bookmark>. После возобновления чтения с закладки действие `ReadLine` присваивает данные, переданные с закладкой <xref:System.Activities.Bookmark>, своему аргументу <xref:System.Activities.Activity%601.Result%2A>. В следующем примере создается рабочий процесс, использующий действие `ReadLine` для получения имени пользователя и его отображения в окне консоли.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#22](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#22)]  
  
 При выполнении действие `ReadLine` создает закладку <xref:System.Activities.Bookmark> с именем `UserName` и ждет возобновления чтения с этой закладки. Узел собирает необходимые данные и возобновляет чтение с закладки <xref:System.Activities.Bookmark>. Рабочий процесс возобновляется, отображает имя и затем завершается.  
  
 Ведущее приложение может проверять рабочий процесс на наличие активных закладок. Это осуществляется вызовом метода <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> экземпляра <xref:System.Activities.WorkflowApplication> или проверкой <xref:System.Activities.WorkflowApplicationIdleEventArgs> в обработчике <xref:System.Activities.WorkflowApplication.Idle%2A>.  
  
 Следующий пример кода подобен предыдущему примеру, за исключением того, что активные закладки перечисляются до возобновления закладки. Рабочий процесс запускается, и, когда создается <xref:System.Activities.Bookmark>, а рабочий процесс переходит в состояние бездействия, вызывается метод <xref:System.Activities.WorkflowApplication.GetBookmarks%2A>. После завершения рабочего процесса на консоль выводятся следующие данные.  
  
 **Как вас зовут?**  
**ЗакладкаИмя: UserName - OwnerDisplayName: ReadLine**
**Стив**
**Здравствуйте, Стив**

[!code-csharp[CFX_WorkflowApplicationExample#14](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#14)]  
  
 В следующем примере кода проверяются аргументы <xref:System.Activities.WorkflowApplicationIdleEventArgs>, переданные в обработчик <xref:System.Activities.WorkflowApplication.Idle%2A> экземпляра <xref:System.Activities.WorkflowApplication>. В этом примере рабочий процесс, переходящий в состояние бездействия, содержит одну закладку <xref:System.Activities.Bookmark> с именем `EnterGuess`, которая принадлежит действию с именем `ReadInt`. Этот пример кода основан на том, [как: Запустить рабочий процесс,](how-to-run-a-workflow.md)который является частью [Начинаюм учебного урока.](getting-started-tutorial.md) Если на данном этапе изменить обработчик <xref:System.Activities.WorkflowApplication.Idle%2A> и включить код из этого примера, то будут выведены следующие данные.  
  
 **BookmarkName: EnterGuess — OwnerDisplayName: ReadInt**

 [!code-csharp[CFX_WorkflowApplicationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#2)]  
  
## <a name="summary"></a>Сводка  
 <xref:System.Activities.WorkflowInvoker> предоставляет упрощенный способ вызова рабочих процессов, и, хотя он предоставляет методы для передачи данных в начале рабочего процесса и извлечения данных из завершенного процесса, он не предусмотрен для более сложных сценариев, в которых можно использовать <xref:System.Activities.WorkflowApplication>.
