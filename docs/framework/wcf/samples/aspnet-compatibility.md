---
title: Совместимость с ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 0938075464a0f2739bdb2a9d8ed1f16f61edff2b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716162"
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="5e42d-102">Совместимость с ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5e42d-102">ASP.NET Compatibility</span></span>

<span data-ttu-id="5e42d-103">В этом примере показано, как включить режим совместимости ASP.NET в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e42d-103">This sample demonstrates how to enable ASP.NET Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5e42d-104">Службы, работающие в режиме совместимости ASP.NET, полностью участвуют в конвейере приложений ASP.NET и могут использовать такие функции ASP.NET, как авторизация файлов и URL-адресов, состояние сеанса и класс <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="5e42d-104">Services running in ASP.NET Compatibility mode participate fully in the ASP.NET application pipeline and can make use of ASP.NET features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="5e42d-105">Класс <xref:System.Web.HttpContext> предоставляет доступ к файлам cookie, сеансам и другим ASP.NET функциям.</span><span class="sxs-lookup"><span data-stu-id="5e42d-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other ASP.NET features.</span></span> <span data-ttu-id="5e42d-106">Для этого режима требуется, чтобы привязки использовали транспорт HTTP, а сами службы были размещены в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5e42d-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>

<span data-ttu-id="5e42d-107">В этом примере клиентом является консольное приложение (как исполняемый файл), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5e42d-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="5e42d-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="5e42d-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="5e42d-109">Для запуска этого примера требуется пул приложений .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5e42d-109">This sample requires a .NET Framework 4 application pool in order to run.</span></span> <span data-ttu-id="5e42d-110">Чтобы создать новый пул приложений или изменить пул приложений по умолчанию, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="5e42d-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>

1. <span data-ttu-id="5e42d-111">Откройте **панель управления**.</span><span class="sxs-lookup"><span data-stu-id="5e42d-111">Open **Control Panel**.</span></span>  <span data-ttu-id="5e42d-112">Откройте приложение **Администрирование** под заголовком **система и безопасность** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="5e42d-113">Откройте приложение **диспетчера службы IIS (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>

2. <span data-ttu-id="5e42d-114">Разверните элемент TreeView в области **подключения** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="5e42d-115">Выберите узел **Пулы приложений** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-115">Select the **Application Pools** node.</span></span>

3. <span data-ttu-id="5e42d-116">Чтобы настроить пул приложений по умолчанию для использования .NET Framework 4 (что может привести к проблемам несовместимости с существующими сайтами), щелкните правой кнопкой мыши элемент списка **DefaultAppPool** и выберите пункт **Основные параметры...** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-116">To set the default application pool to use .NET Framework 4 (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="5e42d-117">Задайте для **версии .NET Framework версию** **.NET Framework v 4.0.30128** (или более позднюю).</span><span class="sxs-lookup"><span data-stu-id="5e42d-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>

4. <span data-ttu-id="5e42d-118">Чтобы создать новый пул приложений, использующий .NET Framework 4 (чтобы сохранить совместимость для других приложений), щелкните правой кнопкой мыши узел **Пулы приложений** и выберите **Добавить пул приложений.** ...</span><span class="sxs-lookup"><span data-stu-id="5e42d-118">To create a new application pool that uses .NET Framework 4 (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="5e42d-119">Присвойте новому пулу приложений имя, а для параметра **версия .NET Framework** — значение **.NET Framework v 4.0.30128** (или более поздней версии).</span><span class="sxs-lookup"><span data-stu-id="5e42d-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="5e42d-120">После выполнения приведенных ниже шагов настройки щелкните правой кнопкой мыши приложение **servicemodelsamples** и выберите **Управление приложением**, **Дополнительные параметры...** .</span><span class="sxs-lookup"><span data-stu-id="5e42d-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="5e42d-121">Задайте для **пула приложений** новый пул приложений.</span><span class="sxs-lookup"><span data-stu-id="5e42d-121">Set the **Application Pool** to the new application pool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e42d-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5e42d-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5e42d-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5e42d-123">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5e42d-124">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="5e42d-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5e42d-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5e42d-125">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`

<span data-ttu-id="5e42d-126">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="5e42d-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="5e42d-127">Контракт `ICalculator` был изменен в соответствии с контрактом `ICalculatorSession`, чтобы можно было выполнять набор операций с сохранением промежуточного результата.</span><span class="sxs-lookup"><span data-stu-id="5e42d-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculatorSession
{
    [OperationContract]
    void Clear();
    [OperationContract]
    void AddTo(double n);
    [OperationContract]
    void SubtractFrom(double n);
    [OperationContract]
    void MultiplyBy(double n);
    [OperationContract]
    void DivideBy(double n);
    [OperationContract]
    double Result();
}
```

<span data-ttu-id="5e42d-128">Благодаря использованию возможности служба поддерживает состояние клиента во время вызова нескольких операций для вычислений.</span><span class="sxs-lookup"><span data-stu-id="5e42d-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="5e42d-129">Клиент может извлечь текущий результат путем вызова метода `Result` и очистить результат (сделать его равным нулю) путем вызова метода `Clear`.</span><span class="sxs-lookup"><span data-stu-id="5e42d-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>

<span data-ttu-id="5e42d-130">Служба использует сеанс ASP.NET для хранения результатов для каждого сеанса клиента.</span><span class="sxs-lookup"><span data-stu-id="5e42d-130">The service uses the ASP.NET session to store the result for each client session.</span></span> <span data-ttu-id="5e42d-131">Это позволяет службе поддерживать промежуточный результат для каждого клиента по мере множественных вызовов службы.</span><span class="sxs-lookup"><span data-stu-id="5e42d-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>

> [!NOTE]
> <span data-ttu-id="5e42d-132">Состояние сеанса ASP.NET и сеансы WCF очень различны.</span><span class="sxs-lookup"><span data-stu-id="5e42d-132">ASP.NET session state and WCF sessions are very different things.</span></span> <span data-ttu-id="5e42d-133">Дополнительные сведения о сеансах WCF см. в разделе [сеанс](../../../../docs/framework/wcf/samples/session.md) .</span><span class="sxs-lookup"><span data-stu-id="5e42d-133">See [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>

<span data-ttu-id="5e42d-134">Служба имеет глубокую зависимость от состояния сеанса ASP.NET и требует режима совместимости ASP.NET для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="5e42d-134">The service has an intimate dependency on ASP.NET session state and requires ASP.NET compatibility mode to function correctly.</span></span> <span data-ttu-id="5e42d-135">Такие требования выражаются декларативно путем применения атрибута `AspNetCompatibilityRequirements`.</span><span class="sxs-lookup"><span data-stu-id="5e42d-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>

```csharp
[AspNetCompatibilityRequirements(RequirementsMode =
                       AspNetCompatibilityRequirementsMode.Required)]
public class CalculatorService : ICalculatorSession
{
    double Result
    {  // store result in AspNet Session
       get {
          if (HttpContext.Current.Session["Result"] != null)
             return (double)HttpContext.Current.Session["Result"];
          return 0.0D;
       }
       set
       {
          HttpContext.Current.Session["Result"] = value;
       }
    }
    public void Clear()
    {
        Result = 0.0D;
    }
    public void AddTo(double n)
    {
        Result += n;
    }
    public void SubtractFrom(double n)
    {
        Result -= n;
    }
    public void MultiplyBy(double n)
    {
        Result *= n;
    }
    public void DivideBy(double n)
    {
        Result /= n;
    }
    public double Result()
    {
        return Result;
    }
}
```

<span data-ttu-id="5e42d-136">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="5e42d-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="5e42d-137">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="5e42d-137">Press ENTER in the client window to shut down the client.</span></span>

```console
0, + 100, - 50, * 17.65, / 2 = 441.25
Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5e42d-138">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5e42d-138">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="5e42d-139">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e42d-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="5e42d-140">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e42d-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="5e42d-141">После построения решения запустите программу Setup. bat, чтобы настроить приложение ServiceModelSamples в IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="5e42d-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="5e42d-142">Теперь каталог ServiceModelSamples должен отображаться как приложение IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="5e42d-142">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="5e42d-143">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5e42d-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e42d-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="5e42d-144">See also</span></span>

- [<span data-ttu-id="5e42d-145">Примеры размещения и сохраняемости AppFabric</span><span class="sxs-lookup"><span data-stu-id="5e42d-145">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
