---
title: Сохраняемый дуплекс
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 3df5ba962ef33594df1eaebc20789fa9e2d35244
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809431"
---
# <a name="durable-duplex"></a><span data-ttu-id="6b23d-102">Сохраняемый дуплекс</span><span class="sxs-lookup"><span data-stu-id="6b23d-102">Durable Duplex</span></span>
<span data-ttu-id="6b23d-103">В этом примере показано, как установить и настроить устойчивый дуплексный обмен сообщениями с помощью действий обмена сообщениями в Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="6b23d-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="6b23d-104">Устойчивый дуплексный обмен сообщениями - это двусторонний обмен сообщениями в течение длительного времени.</span><span class="sxs-lookup"><span data-stu-id="6b23d-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="6b23d-105">Длительность обмена сообщениями может превышать время существования коммуникационного канала и время существования экземпляров службы в памяти.</span><span class="sxs-lookup"><span data-stu-id="6b23d-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="6b23d-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="6b23d-106">Sample Details</span></span>  
 <span data-ttu-id="6b23d-107">В этом примере две службы Windows Communication Foundation (WCF), реализованный с помощью Windows Workflow Foundation настраиваются иметь устойчивый дуплексный обмен сообщениями.</span><span class="sxs-lookup"><span data-stu-id="6b23d-107">In this sample, two Windows Communication Foundation (WCF) services implemented using Windows Workflow Foundation are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="6b23d-108">Устойчивый дуплексный обмен сообщениями состоит из двух односторонних обменов сообщениями по MSMQ, сопоставляются с помощью [обмен контекстом .NET](http://go.microsoft.com/fwlink/?LinkID=166059).</span><span class="sxs-lookup"><span data-stu-id="6b23d-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="6b23d-109">Сообщения отправляются посредством действий по обмену сообщениями <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>.</span><span class="sxs-lookup"><span data-stu-id="6b23d-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="6b23d-110">Обмен контекстом .NET используется для указания адреса обратного вызова в отправленных сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6b23d-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="6b23d-111">Обе службы размещаются при помощи служб активации процессов Windows WAS и настраиваются на включение сохраняемости экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="6b23d-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="6b23d-112">Первая служба (Service1.xamlx) отправляет в службу отправки (Service2.xamlx) запрос на выполнение задания.</span><span class="sxs-lookup"><span data-stu-id="6b23d-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="6b23d-113">После выполнения задания служба Service2.xamlx уведомляет об этом службу Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6b23d-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="6b23d-114">Приложение командной строки рабочего процесса настраивает прослушиваемые службами очереди и отправляет исходное сообщение "Start", активирующее службу Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6b23d-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="6b23d-115">Получив уведомление о выполнения задания от службы Service2.xamlx, служба Service1.xamlx сохраняет результат в виде XML-файла.</span><span class="sxs-lookup"><span data-stu-id="6b23d-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="6b23d-116">В ожидании сообщения обратного вызова служба Service1.xamlx сохраняет состояние своего экземпляра при помощи <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6b23d-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="6b23d-117">Служба Service1.xamlx сохраняет состояние своего экземпляра при завершении задания, выполнение которого запрошено службой Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6b23d-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="6b23d-118">Чтобы обе службы могли использовать обмен контекстом .NET по MSMQ, они настраиваются на использование пользовательской привязки, состоящей из элементов <xref:System.ServiceModel.Channels.ContextBindingElement> и <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="6b23d-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="6b23d-119">При помощи элемента <xref:System.ServiceModel.Channels.ContextBindingElement> задается адрес обратного вызова, включаемый в соответствующий заголовок всех сообщений, отправляемых при помощи пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="6b23d-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="6b23d-120">Пользовательская привязка определяется в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6b23d-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="6b23d-121">Такая привязка не безопасна.</span><span class="sxs-lookup"><span data-stu-id="6b23d-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="6b23d-122">При развертывании приложения следует настроить пользовательскую привязку, исходя из требований к безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="6b23d-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b23d-123">Используемые в данном образце очереди не являются транзакционными.</span><span class="sxs-lookup"><span data-stu-id="6b23d-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="6b23d-124">Пример, в котором показано, как настроить обмен сообщениями WCF, с использованием очередей транзакции, в разделе [активации MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md) образца.</span><span class="sxs-lookup"><span data-stu-id="6b23d-124">For a sample that shows how to set up WCF message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="6b23d-125">Сообщение от службы Service1.xamlx службе Service2.xamlx отправляется через конечную точку клиента, настроенную на адрес службы Service2.xamlx и на определенную ранее пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="6b23d-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="6b23d-126">Обратный вызов от Service2.xamlx службе Service1.xamlx отправляется через конечную точку клиента, не настроенную явно на адрес, так как адрес получается из контекста обратного вызова, отправленного службой Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6b23d-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="6b23d-127">Конечные точки клиента определяются в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6b23d-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6b23d-128">В следующем примере кода конечные точки, использующие данную пользовательскую привязку, предоставляются посредством изменения стандартного сопоставления протокола для базовых адресов net.msmq, которые будут использовать данную пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="6b23d-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6b23d-129">В следующем примере кода активируется сохраняемость для обеих служб путем добавления к ним поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> и указания строки подключения к базе данных сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="6b23d-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="6b23d-130">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="6b23d-130">System Requirements</span></span>  
 <span data-ttu-id="6b23d-131">Для данного образца требуются следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="6b23d-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="6b23d-132">Службы IIS.</span><span class="sxs-lookup"><span data-stu-id="6b23d-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="6b23d-133">Службы IIS -> Совместимость управления IIS 6.0 -> Метабаза IIS и совместимость конфигурации IIS 6.0.</span><span class="sxs-lookup"><span data-stu-id="6b23d-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="6b23d-134">Веб-службы -> Компоненты разработки приложений -> ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6b23d-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="6b23d-135">Сервер очереди сообщений (Майкрософт) (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="6b23d-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6b23d-136">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="6b23d-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="6b23d-137">Настройте базы данных сохраняемости и каталог результатов.</span><span class="sxs-lookup"><span data-stu-id="6b23d-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="6b23d-138">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b23d-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="6b23d-139">Перейдите в каталог образцов и запустите команду Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="6b23d-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="6b23d-140">Настройте виртуальное приложение.</span><span class="sxs-lookup"><span data-stu-id="6b23d-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="6b23d-141">Введите в командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] следующую команду, чтобы зарегистрировать ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6b23d-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="6b23d-142">Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с разрешениями администратора, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и выбрав **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="6b23d-143">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл DurableDuplex.sln.</span><span class="sxs-lookup"><span data-stu-id="6b23d-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="6b23d-144">Настройте очереди обслуживания.</span><span class="sxs-lookup"><span data-stu-id="6b23d-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="6b23d-145">Чтобы запустить клиент DurableDuplex, нажмите кнопку F5.</span><span class="sxs-lookup"><span data-stu-id="6b23d-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="6b23d-146">Откройте **Управление компьютером** консоли, выполнив `Compmgmt.msc` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6b23d-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="6b23d-147">Разверните **службы и приложения**, **очереди сообщений**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="6b23d-148">**Частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="6b23d-149">Щелкните правой кнопкой мыши очереди durableduplex/service1.xamlx и durableduplex/service2.xamlx и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="6b23d-150">Выберите **безопасности** вкладку и разрешить **получение сообщения**, **Просмотр сообщения** и **Отправка сообщения** обоим очередям права.</span><span class="sxs-lookup"><span data-stu-id="6b23d-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="6b23d-151">Откройте диспетчер служб IIS.</span><span class="sxs-lookup"><span data-stu-id="6b23d-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="6b23d-152">Перейдите к **сервера**, **сайтов**, **по умолчанию веб-сайт**, **закрытый**, **устойчивый дуплекс** и выберите пункт **Дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="6b23d-153">Изменение **включенные протоколы** для **http,net.msmq**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="6b23d-154">Выполните образец.</span><span class="sxs-lookup"><span data-stu-id="6b23d-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="6b23d-155">Перейдите к http://localhost/private/durableduplex/service1.xamlx и http://localhost/private/durableduplex/service2.xamlx чтобы убедиться, что оба они работают.</span><span class="sxs-lookup"><span data-stu-id="6b23d-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="6b23d-156">Чтобы запустить DurableDuplexClient, нажмите кнопку F5.</span><span class="sxs-lookup"><span data-stu-id="6b23d-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="6b23d-157">По завершению устойчивого дуплексного обмена сообщениями в каталоге C:\Inbox сохраняется файл result.xml с результатами обмена.</span><span class="sxs-lookup"><span data-stu-id="6b23d-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="6b23d-158">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="6b23d-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="6b23d-159">Запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="6b23d-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="6b23d-160">Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b23d-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="6b23d-161">Перейдите в каталог образцов и запустите команду Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="6b23d-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="6b23d-162">Удалите виртуальное приложение служб.</span><span class="sxs-lookup"><span data-stu-id="6b23d-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="6b23d-163">Откройте диспетчер Internet Information Services (IIS), запустив `Inetmgr.exe` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6b23d-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="6b23d-164">Перейдите на веб-сайт по умолчанию и удалить **закрытый** виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="6b23d-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="6b23d-165">Удалите заданные для данного образца очереди.</span><span class="sxs-lookup"><span data-stu-id="6b23d-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="6b23d-166">Откройте консоль управления компьютером, запустив `Compmgmt.msc` из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6b23d-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="6b23d-167">Разверните **службы и приложения**, **очереди сообщений**, **частные очереди**.</span><span class="sxs-lookup"><span data-stu-id="6b23d-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="6b23d-168">Удалите очереди durableduplex/service1.xamlx и durableduplex/service2.xamlx.</span><span class="sxs-lookup"><span data-stu-id="6b23d-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="6b23d-169">Удалите каталог C:\Inbox.</span><span class="sxs-lookup"><span data-stu-id="6b23d-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6b23d-170">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6b23d-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6b23d-171">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6b23d-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6b23d-172">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="6b23d-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6b23d-173">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6b23d-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`