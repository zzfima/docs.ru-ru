---
title: Настройка отслеживания рабочего процесса
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 25edef2edc23a3823a892c64809df21f333478db
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458897"
---
# <a name="configuring-tracking-for-a-workflow"></a>Настройка отслеживания рабочего процесса

Рабочий процесс может выполняться тремя способами.

- Размещаться в <xref:System.ServiceModel.Activities.WorkflowServiceHost>

- Выполняться в виде приложения <xref:System.Activities.WorkflowApplication>.

- Выполняться напрямую с использованием <xref:System.Activities.WorkflowInvoker>

В зависимости от выбранного варианта размещения рабочего процесса участник отслеживания может быть добавлен как посредством кода, так и через файл конфигурации. В этом разделе описывается, как настроить отслеживание посредством добавления участника отслеживания в <xref:System.Activities.WorkflowApplication> и в <xref:System.ServiceModel.Activities.WorkflowServiceHost>, и как включить режим отслеживания с помощью <xref:System.Activities.WorkflowInvoker>.

## <a name="configuring-workflow-application-tracking"></a>Настройка отслеживания приложений рабочих процессов

Запустить рабочий процесс можно с использованием приложения <xref:System.Activities.WorkflowApplication>. В этом разделе показывается, как настраивается отслеживание для приложения рабочего процесса [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] путем добавления участника отслеживания в узел рабочего процесса <xref:System.Activities.WorkflowApplication>. В этом случае рабочий процесс выполняется как приложение рабочего процесса. Приложение рабочего процесса можно настроить посредством кода (без использования файла конфигурации), представляющего собой резидентный EXE-файл, использующий класс <xref:System.Activities.WorkflowApplication>. Участник отслеживания добавляется как расширение для экземпляра <xref:System.Activities.WorkflowApplication>. Это выполняется путем добавления <xref:System.Activities.Tracking.TrackingParticipant> в коллекцию расширений для экземпляра WorkflowApplication.

Для приложения рабочего процесса можно добавить расширение поведения <xref:System.Activities.Tracking.EtwTrackingParticipant>, как это показано в следующем коде.

```csharp
LogActivity activity = new LogActivity();

WorkflowApplication instance = new WorkflowApplication(activity);
EtwTrackingParticipant trackingParticipant =
    new EtwTrackingParticipant
{

        TrackingProfile = new TrackingProfile
           {
               Name = "SampleTrackingProfile",
               ActivityDefinitionId = "ProcessOrder",
               Queries = new WorkflowInstanceQuery
               {
                  States = { "*" }
              }
          }
       };
instance.Extensions.Add(trackingParticipant);
```

### <a name="configuring-workflow-service-tracking"></a>Настройка отслеживания службы рабочего процесса

Рабочий процесс может быть представлен как служба WCF при размещении на узле службы <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Класс <xref:System.ServiceModel.Activities.WorkflowServiceHost> является специализированной реализацией класса ServiceHost библиотеки .NET для службы на основе рабочих процессов. В этом разделе описывается настройка отслеживания для службы рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], выполняющейся в <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Его настройка осуществляется с использованием файла Web.config (для служб, размещаемых на веб-сервере) или файла App.config (для служб, размещаемых в автономном приложении, например, в консольном приложении) посредством определения поведения службы или задания кода путем добавления поведения, связанного с отслеживанием, в коллекцию <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> для узла службы.

Для службы рабочего процесса, размещенной в <xref:System.ServiceModel.WorkflowServiceHost>, можно добавить <xref:System.Activities.Tracking.EtwTrackingParticipant> с помощью элемента <`behavior`> в файле конфигурации, как показано в следующем примере.

```xml
<behaviors>
   <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
   </serviceBehaviors>
</behaviors>
```

Также для службы рабочего процесса, размещенной в <xref:System.ServiceModel.WorkflowServiceHost>, можно добавить расширение поведения <xref:System.Activities.Tracking.EtwTrackingParticipant> посредством кода. Для добавления пользовательского участника отслеживания создайте новое расширение поведения и добавьте его в <xref:System.ServiceModel.ServiceHost>, как это показано в следующем примере кода.

> [!NOTE]
> Если вы хотите просмотреть пример кода, показывающий, как создать пользовательский элемент поведения, который добавляет настраиваемый участник отслеживания, обратитесь к примерам [отслеживания](./samples/tracking.md) .

```csharp
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new
                                 Uri("http://localhost:8001/Sample"));
EtwTrackingBehavior trackingBehavior =
    new EtwTrackingBehavior
    {
        ProfileName = "Sample Tracking Profile"
    };
svcHost.Description.Behaviors.Add(trackingBehavior);
svcHost.Open();
```

Участник отслеживания добавляется к узлу службы рабочего процесса, как расширение поведения.

В образце кода ниже показано считывание профиля отслеживания из файла конфигурации.

```csharp
TrackingProfile GetProfile(string profileName, string displayName)
        {
            TrackingProfile trackingProfile = null;
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");
            if (trackingSection == null)
            {
                return null;
            }

            profileName ??= "";

            //Find the profile with the specified profile name in the list of profile found in config
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))
                        select p;

            if (match.Count() == 0)
            {
                //return an empty profile
                trackingProfile = new TrackingProfile()
                {
                    ActivityDefinitionId = displayName
                };

            }
            else
            {
                trackingProfile = match.First();
            }

            return trackingProfile;
```

В образце кода ниже показано добавление профиля отслеживания к узлу рабочего процесса.

```csharp
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;
if (null != workflowServiceHost)
{
    string workflowDisplayName = workflowServiceHost.Activity.DisplayName;
    TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);
    workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant {
        TrackingProfile = trackingProfile
    });
 }
```

> [!NOTE]
> Дополнительные сведения о профилях отслеживания см. в статье [Профили отслеживания](https://go.microsoft.com/fwlink/?LinkId=201310).

### <a name="configuring-tracking-using-workflowinvoker"></a>Конфигурирование отслеживания с помощью WorkflowInvoker

Чтобы сконфигурировать отслеживание для рабочего процесса, выполняемого с использованием <xref:System.Activities.WorkflowInvoker>, в экземпляр <xref:System.Activities.WorkflowInvoker> добавляется поставщик отслеживания. В следующем примере кода из примера [Custom Tracking](./samples/custom-tracking.md) .

```csharp
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
invoker.Invoke();
```

### <a name="viewing-tracking-records-in-event-viewer"></a>Просмотр записей отслеживания в обозревателе событий

Особый интерес представляют два журнала средства просмотра при отслеживании выполнения WF - аналитический журнал и журнал отладки. Оба находятся в узле сервер&#124;приложений&#124;Microsoft Windows — приложения. В этом разделе журналы содержат события из одного приложения, а не события, влияющие на всю систему.

События трассировки отладки записываются в журнал отладки. Для получения событий трассировки отладки WF в средстве просмотра включите журнал отладки.

1. Чтобы открыть Просмотр событий, нажмите кнопку **Пуск**и выберите команду **выполнить.** В диалоговом окне Выполнить введите `eventvwr`.

2. В диалоговом окне Просмотр событий разверните узел **журналы приложений и служб** .

3. Разверните узлы **Microsoft**, **Windows**и **сервер приложений — приложения** .

4. Щелкните правой кнопкой мыши узел **Отладка** в узле **сервер приложений — приложения** и выберите **Включить журнал**.

5. Чтобы сформировать события трассировки, запустите приложение с включенной функцией трассировки.

6. Щелкните правой кнопкой мыши узел **Отладка** и выберите команду **Обновить.** На центральную панель будут выведены события трассировки.

WF 4 предоставляет участника отслеживания, который пишет записи трассировки в сеанс ETW (средство трассировки событий для Windows). Для подписки на записи отслеживания в участнике отслеживания трассировка событий Windows задается профиль отслеживания. Если включено отслеживание ошибок, записи отслеживания создаются в трассировке событий Windows. События трассировки событий Windows (в диапазоне 100–113), соответствующие событиям отслеживания, выпущенным участником отслеживания трассировки событий Windows, записываются в аналитический журнал.

Чтобы просмотреть записи отслеживания, выполните следующие действия.

1. Чтобы открыть Просмотр событий, нажмите кнопку **Пуск**и выберите команду **выполнить.** В диалоговом окне Выполнить введите `eventvwr`.

2. В диалоговом окне Просмотр событий разверните узел **журналы приложений и служб** .

3. Разверните узлы **Microsoft**, **Windows**и **сервер приложений — приложения** .

4. Щелкните правой кнопкой мыши узел **аналитики** в узле **сервер приложений — приложения** и выберите **Включить журнал**.

5. Чтобы сформировать записи отслеживания, запустите приложение с включенной функцией отслеживания.

6. Щелкните правой кнопкой мыши **аналитический** узел и выберите **Обновить.** В центральную область будут выведены записи отслеживания.

На следующем рисунке показаны события отслеживания в средстве просмотра событий.

![Снимок экрана Просмотр событий, отображающий записи отслеживания.](./media/configuring-tracking-for-a-workflow/tracking-event-viewer.png)

### <a name="registering-an-application-specific-provider-id"></a>Регистрация идентификатора поставщика конкретного приложения

Если сведения о событии нужно заносить в журнал конкретного приложения, для регистрации манифеста нового поставщика необходимо выполнить следующие действия.

1. Укажите идентификатор поставщика в файле конфигурации приложения.

    ```xml
    <system.serviceModel>
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>
    </system.serviceModel>
    ```

2. Скопируйте файл манифеста из%windir%\Microsoft.NET\Framework\\\<последнюю версию [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Микрософт.Виндовс.аппликатионсервер.аппликатионс.Ман во временное расположение и переименуйте ее в Microsoft. Windows. ApplicationServer. Applications_Provider1. Man

3. Замените идентификатор GUID в файле манифеста на новый идентификатор.

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

4. Если вы не хотите удалять поставщик по умолчанию, измените имя поставщика.

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"
    ```

5. Если на предыдущем шаге имя поставщика было изменено, измените имена каналов в файле манифеста на имя нового поставщика.

    ```xml
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />
    ```

6. Сформируйте DLL-библиотеку ресурсов, выполнив следующие действия.

    1. Установите пакет Windows SDK. Windows SDK включает компилятор сообщений ([MC. exe](https://go.microsoft.com/fwlink/?LinkId=184606)) и компилятор ресурсов ([RC. exe](https://go.microsoft.com/fwlink/?LinkId=184605)).

    2. В командной строке Windows SDK примените команду run mc.exe к новому файлу манифеста.

        ```console
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

    3. Примените команду rc.exe к файлу ресурсов, сформированному на предыдущем шаге.

        ```console
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc
        ```

    4. Создайте пустой файл CS с именем NewProviderReg.cs.

    5. Создайте DLL-библиотеку ресурсов с помощью компилятора C#.

        ```console
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll
        ```

    6. Измените имя DLL ресурса и сообщения в файле манифеста с `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` на новое имя библиотеки DLL.

        ```xml
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll">
        ```

    7. Для регистрации манифеста используйте средство [wevtutil](https://go.microsoft.com/fwlink/?LinkId=184608) .

        ```console
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

## <a name="see-also"></a>См. также

- [Мониторинг Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Мониторинг приложений с помощью App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
