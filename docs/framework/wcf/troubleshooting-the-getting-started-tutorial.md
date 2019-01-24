---
title: Устранение неполадок, связанных с руководством по началу работы
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 5b8cd04ef4d98e522e255e1b7529e848351b2e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695664"
---
# <a name="troubleshooting-the-getting-started-tutorial"></a><span data-ttu-id="9e056-102">Устранение неполадок, связанных с руководством по началу работы</span><span class="sxs-lookup"><span data-stu-id="9e056-102">Troubleshooting the Getting Started Tutorial</span></span>
<span data-ttu-id="9e056-103">В этом разделе рассматриваются наиболее распространенные проблемы, которые возникают при работе с учебником «Приступая к работе», и описываются способы их решения.</span><span class="sxs-lookup"><span data-stu-id="9e056-103">This topic lists the most common problems encountered when working through the Getting Started Tutorial and how to resolve them.</span></span>  
  
<span data-ttu-id="9e056-104">**Не удается найти файлы проекта на жестком диске.**</span><span class="sxs-lookup"><span data-stu-id="9e056-104">**I am unable to find the project files on my hard drive.**</span></span>

 <span data-ttu-id="9e056-105">Visual Studio сохраняет файлы проекта c:\users\\<user name>\Documents\\< версия Visual Studio\>\Projects.</span><span class="sxs-lookup"><span data-stu-id="9e056-105">Visual Studio saves project files in c:\users\\<user name>\Documents\\<Visual Studio version\>\Projects.</span></span>  
  
<span data-ttu-id="9e056-106">**Попытка запуска служебного приложения: HTTP не удалось зарегистрировать URL-адрес `http://+:8000/ServiceModelSamples/Service/`.** 
 **Ваш процесс не имеет прав доступа к этому пространству имен.**</span><span class="sxs-lookup"><span data-stu-id="9e056-106">**Attempting to run the service application: HTTP could not register URL `http://+:8000/ServiceModelSamples/Service/`.**
**Your process does not have access rights to this namespace.**</span></span> 

 <span data-ttu-id="9e056-107">Процесс, на котором размещена служба WCF должна выполняться с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9e056-107">The process that hosts a WCF service must be run with Administrative privileges.</span></span> <span data-ttu-id="9e056-108">Если при запуске службы из внутри Visual Studio, необходимо запустить Visual Studio с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9e056-108">If you are running the service from inside Visual Studio, you must run Visual Studio as an Administrator.</span></span> <span data-ttu-id="9e056-109">Для этого нажмите кнопку **запустить**, щелкните правой кнопкой мыши **Visual Studio \< *версии* >**  и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9e056-109">To do so click **Start**, right-click **Visual Studio \<*version*>** and select **Run As Administrator**.</span></span> <span data-ttu-id="9e056-110">При запуске службы из командной строки в окне консоли, так же, как необходимо запустить в окне консоли с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9e056-110">If you are running the service from a command-line prompt in a console window, you must start the console window as an Administrator in a similar way.</span></span> <span data-ttu-id="9e056-111">Нажмите кнопку **запустить**, щелкните правой кнопкой мыши **командной** и выберите **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="9e056-111">Click **Start**, right-click **Command Prompt** and select **Run As Administrator**.</span></span>  
  
<span data-ttu-id="9e056-112">**Попытка использования средства Svcutil.exe: 'svcutil' не распознается как внутренняя или внешняя команда, исполняемая программа или пакетный файл.**</span><span class="sxs-lookup"><span data-stu-id="9e056-112">**Attempting to use the Svcutil.exe tool: 'svcutil' is not recognized as an internal or external command, operable program or batch file.**</span></span>

 <span data-ttu-id="9e056-113">Файл Svcutil.exe должен быть расположен в системной папке.</span><span class="sxs-lookup"><span data-stu-id="9e056-113">Svcutil.exe must be in the system path.</span></span> <span data-ttu-id="9e056-114">Самым простым решением является использование командной строки.</span><span class="sxs-lookup"><span data-stu-id="9e056-114">The easiest solution is to use the Command Prompt.</span></span> <span data-ttu-id="9e056-115">Нажмите кнопку **запустить**выберите **все программы**, **Visual Studio \< *версии*>**,  **Инструменты Visual Studio**, и **Командная строка разработчика для Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="9e056-115">Click **Start**, select **All Programs**, **Visual Studio \<*version*>**, **Visual Studio Tools**, and **Developer Command Prompt for Visual Studio**.</span></span> <span data-ttu-id="9e056-116">Эта командная строка задает системный путь правильное расположение для всех средств, поставляемых в составе Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9e056-116">This command prompt sets the system path to the correct locations for all tools shipped as part of Visual Studio.</span></span>  

<span data-ttu-id="9e056-117">**Не удалось найти файл App.config, созданный средством Svcutil.exe.**</span><span class="sxs-lookup"><span data-stu-id="9e056-117">**Unable to find the App.config file generated by Svcutil.exe.**</span></span>

 <span data-ttu-id="9e056-118">**Добавить существующий элемент** диалоговое окно отображает только файлы со следующими расширениями по умолчанию: .cs, .resx, с расширением Settings, XSD-файл, WSDL-файлы.</span><span class="sxs-lookup"><span data-stu-id="9e056-118">The **Add Existing Item** dialog only displays files with the following extensions by default: .cs, .resx, .settings, .xsd, .wsdl.</span></span> <span data-ttu-id="9e056-119">Можно указать, что вы хотите увидеть все типы файлов, выбрав **все файлы (\*.\*)**  в раскрывающемся списке в правом нижнем углу **добавить существующий элемент** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9e056-119">You can specify that you want to see all file types by selecting **All Files (\*.\*)** in the drop-down list box in the lower right corner of the **Add Existing Item** dialog box.</span></span>  


<span data-ttu-id="9e056-120">**Компиляция клиентского приложения: 'CalculatorClient' не содержит определение для "\<имя метода >" и метод расширения "\<имя метода >" принимающий первый аргумент типа 'CalculatorClient' может быть найден (возможно, отсутствует using директива или ссылка на сборку?)**</span><span class="sxs-lookup"><span data-stu-id="9e056-120">**Compiling the client application: 'CalculatorClient' does not contain a definition for '\<method name>' and no extension method '\<method name>' accepting a first argument of type 'CalculatorClient' could be found (are you missing a using directive or an assembly reference?)**</span></span>  

<span data-ttu-id="9e056-121">Только методы, отмеченные атрибутом `ServiceOperationAttribute`, доступны для внешнего использования.</span><span class="sxs-lookup"><span data-stu-id="9e056-121">Only those methods that are marked with the `ServiceOperationAttribute` are exposed to the outside world.</span></span> <span data-ttu-id="9e056-122">Если вы пропустили `ServiceOperationAttribute` атрибут из одного из методов в `ICalculator` интерфейса, вы получаете это сообщение об ошибке при компиляции клиентского приложения, которое вызывает операции, при отсутствии этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="9e056-122">If you omitted the `ServiceOperationAttribute` attribute from one of the methods in the `ICalculator` interface, you get this error message when compiling a client application that makes a call to the operation missing the attribute.</span></span>  

<span data-ttu-id="9e056-123">**Компиляция клиентского приложения: Имя типа или пространства имен 'CalculatorClient' не найден (возможно, отсутствует using директива или ссылка на сборку?)**</span><span class="sxs-lookup"><span data-stu-id="9e056-123">**Compiling the client application: The type or namespace name 'CalculatorClient' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

 <span data-ttu-id="9e056-124">Эта ошибка возникает, если в проект клиента не добавлен файл Proxy.cs или Proxy.vb.</span><span class="sxs-lookup"><span data-stu-id="9e056-124">You get this error if you do not add the Proxy.cs or Proxy.vb file to your client project.</span></span>  

<span data-ttu-id="9e056-125">**Под управлением клиента: необработанное исключение: System.ServiceModel.EndpointNotFoundException: Не удалось подключиться к `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. Код ошибки TCP 10061: Не удалось установить соединение, так как конечный компьютер отверг.**</span><span class="sxs-lookup"><span data-stu-id="9e056-125">**Running the client: Unhandled Exception: System.ServiceModel.EndpointNotFoundException: Could not connect to `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`. TCP error code 10061: No connection could be made because the target machine actively refused it.**</span></span>

<span data-ttu-id="9e056-126">Эта ошибка возникает в случае запуска клиентского приложения без запуска службы.</span><span class="sxs-lookup"><span data-stu-id="9e056-126">This error occurs if you run the client application without running the service.</span></span>  
  
<span data-ttu-id="9e056-127">**Необработанное исключение: System.ServiceModel.Security.SecurityNegotiationException: Согласования безопасности SOAP с `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` для целевого объекта `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` не удалось**</span><span class="sxs-lookup"><span data-stu-id="9e056-127">**Unhandled Exception: System.ServiceModel.Security.SecurityNegotiationException: SOAP security negotiation with `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` for target `http://localhost:8000/ServiceModelSamples/Service/CalculatorService` failed**</span></span>  

<span data-ttu-id="9e056-128">Эта ошибка происходит на присоединенном к домену компьютере, который не подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="9e056-128">This error occurs on a domain-joined computer that does not have network connectivity.</span></span> <span data-ttu-id="9e056-129">Подключите компьютер к сети или отключите безопасность для клиента и для службы.</span><span class="sxs-lookup"><span data-stu-id="9e056-129">Either connect your computer to the network or turn off security for both the client and the service.</span></span> <span data-ttu-id="9e056-130">Для службы замените код, создающий WSHttpBinding, на следующий.</span><span class="sxs-lookup"><span data-stu-id="9e056-130">For the service, modify the code that creates the WSHttpBinding to the following.</span></span>  
  
```csharp
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```

<span data-ttu-id="9e056-131">Для клиента, измените  **\<безопасности >** элемента под  **\<привязки >** элемент следующего:</span><span class="sxs-lookup"><span data-stu-id="9e056-131">For the client, change the **\<security>** element under the **\<binding>** element to the following:</span></span>  
  
```xml
<security mode="Node" />  
```  

## <a name="see-also"></a><span data-ttu-id="9e056-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9e056-132">See also</span></span>
- [<span data-ttu-id="9e056-133">Руководство по началу работы</span><span class="sxs-lookup"><span data-stu-id="9e056-133">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)
- [<span data-ttu-id="9e056-134">Примеры устранения неполадок WCF</span><span class="sxs-lookup"><span data-stu-id="9e056-134">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)
- [<span data-ttu-id="9e056-135">Устранение неполадок с установкой</span><span class="sxs-lookup"><span data-stu-id="9e056-135">Troubleshooting Setup Issues</span></span>](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
