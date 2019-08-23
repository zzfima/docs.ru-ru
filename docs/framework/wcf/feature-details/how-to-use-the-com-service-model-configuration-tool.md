---
title: Практическое руководство. Использование программы командной строки настройки модели служб COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: 9677e516ef6c91ef344e10bc8f608a397a4ed157
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966135"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a><span data-ttu-id="68d02-102">Практическое руководство. Использование программы командной строки настройки модели служб COM+</span><span class="sxs-lookup"><span data-stu-id="68d02-102">How to: Use the COM+ Service Model Configuration Tool</span></span>
<span data-ttu-id="68d02-103">Выбрав нужный режим размещения, с помощью программы командной строки настройки модели служб COM+ (ComSvcConfig.exe) сконфигурируйте интерфейсы приложения, предоставляемые как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-103">Once you have selected an appropriate hosting mode, use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that will be exposed as Web services.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68d02-104">Для выполнения каждой из следующих задач необходимо быть администратором компьютера.</span><span class="sxs-lookup"><span data-stu-id="68d02-104">You must be an administrator on the machine to perform any of the following tasks.</span></span>  
  
 <span data-ttu-id="68d02-105">При использовании ComSvcConfig.exe на компьютере под управлением Windows 7 для настройки веб-службы на использование последней версии модели службы (в настоящее время v4.5) выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="68d02-105">When using ComSvcConfig.exe on a Windows 7 machine to configure a web service to use the latest service model version (currently v4.5), perform the following steps:</span></span>  
  
1. <span data-ttu-id="68d02-106">Присвойте разделу `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` реестра значение DWORD 0x00000001.</span><span class="sxs-lookup"><span data-stu-id="68d02-106">Set the registry key  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` to a DWORD value of 0x00000001</span></span>  
  
2. <span data-ttu-id="68d02-107">Запустите comsvcconfig.exe</span><span class="sxs-lookup"><span data-stu-id="68d02-107">Run comsvcconfig.exe</span></span>  
  
3. <span data-ttu-id="68d02-108">Верните ключу реестра, добавленному на шаге 1, исходное значение или удалите его, если нет.</span><span class="sxs-lookup"><span data-stu-id="68d02-108">Revert the registry key added in step 1 back to its original value, or delete it if did not exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="68d02-109">Восстановление значения ключа - важно.</span><span class="sxs-lookup"><span data-stu-id="68d02-109">Reverting this registry key is important.</span></span> <span data-ttu-id="68d02-110">Это ключ совместимости.</span><span class="sxs-lookup"><span data-stu-id="68d02-110">This is a compatibility key.</span></span> <span data-ttu-id="68d02-111">Если не восстановить значение ключа, могут возникнуть проблемы в работе других приложений .NET на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="68d02-111">Not reverting this change may cause issues with other .NET applications running on the machine).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="68d02-112">При использовании программы ComSvcConfig. exe/Install на компьютере с Windows 8 появляется диалоговое окно "для приложения на вашем компьютере требуется следующая функция Windows: .NET Framework 3,5 (включает .NET 2,0 и .NET 3,0", если .NET Framework 3,5 не установлен.</span><span class="sxs-lookup"><span data-stu-id="68d02-112">When using ComSvcConfig.exe  /install on a Windows 8 machine a dialog is displayed stating "An app on your PC needs the following Windows feature: .NET Framework 3.5 (includes .NET 2.0 and .NET 3.0" if .NET Framework 3.5 is not installed.</span></span> <span data-ttu-id="68d02-113">Это диалоговое окно можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="68d02-113">This dialog may be ignored.</span></span> <span data-ttu-id="68d02-114">В качестве альтернативы можно задать ключу реестра OnlyUseLatestCLR значение DWORD 0x00000001</span><span class="sxs-lookup"><span data-stu-id="68d02-114">Alternatively you can sed the OnlyUseLatestCLR registry key to a DWORD value of 0x00000001</span></span>  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="68d02-115">Добавление интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения COM+</span><span class="sxs-lookup"><span data-stu-id="68d02-115">To add an interface to the set of interfaces that are to be exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="68d02-116">Выполните программу ComSvcConfig с параметрами `/install` и `/hosting:complus`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-116">Run ComSvcConfig using the `/install` and `/hosting:complus` options, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="68d02-117">Эта команда добавляет интерфейс `IFinances` компонента `ItemOrders.IFinancial` (из приложения COM+ OnlineStore) в набор интерфейсов, предоставляемых как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-117">The command adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="68d02-118">Данная служба использует режим размещения COM+, а потому для нее требуется явное включение приложения.</span><span class="sxs-lookup"><span data-stu-id="68d02-118">The service uses the COM+ hosting mode and therefore requires explicit application activation.</span></span>  
  
     <span data-ttu-id="68d02-119">Можно использовать подстановочный знак - звездочку (\*) для компонента и интерфейса, однако это не рекомендуется, поскольку зачастую желательно предоставлять в качестве веб-службы лишь определенный набор функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="68d02-119">While the wildcard asterisk (\*) character can be used for the component and the interface, avoid using it because you might want to expose only selected functionality as a Web service.</span></span> <span data-ttu-id="68d02-120">При использовании с более новой версией компонента подстановочный знак может (вопреки замыслу разработчика) предоставить интерфейсы, отсутствовавшие на момент определения синтаксиса конфигурации.</span><span class="sxs-lookup"><span data-stu-id="68d02-120">If run with a future version of this component, using the wildcard may unintentionally expose interfaces that may not have been present when the configuration syntax was determined.</span></span>  
  
     <span data-ttu-id="68d02-121">При использовании параметра /verbose программа отображает предупреждения (помимо ошибок).</span><span class="sxs-lookup"><span data-stu-id="68d02-121">The /verbose option instructs the tool to display warnings in addition to any errors.</span></span>  
  
     <span data-ttu-id="68d02-122">Контракт для предоставленной службы содержит все методы интерфейса `IFinances`.</span><span class="sxs-lookup"><span data-stu-id="68d02-122">The contract for the exposed service will contain all of the methods from the `IFinances` interface.</span></span>  
  
### <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="68d02-123">Добавление только определенных методов интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения COM+</span><span class="sxs-lookup"><span data-stu-id="68d02-123">To add only specific methods from an interface to the set of interfaces that are to be exposed as Web services, using the COM+ hosting mode</span></span>  
  
- <span data-ttu-id="68d02-124">Запустите программу ComSvcConfig с параметрами `/install` и `/hosting:complus`, явно указав имена требуемых методов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-124">Run ComSvcConfig using the `/install` and `/hosting:complus` options with explicit naming of the required methods, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="68d02-125">Эта команда добавляет только методы `Credit` и `Debit` из интерфейса `IFinances` как операции в контракт предоставляемой службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-125">The command adds only the `Credit` and `Debit` methods from the `IFinances` interface as operations to the exposed service contract.</span></span> <span data-ttu-id="68d02-126">Все прочие методы интерфейса не добавляются в контракт и не вызываются клиентами веб-службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-126">All other methods on the interface will be omitted from the contract and will not be callable from Web service clients.</span></span>  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-web-hosting-mode"></a><span data-ttu-id="68d02-127">Добавление интерфейса в набор интерфейсов, предоставляемых как веб-службы, с помощью режима размещения на веб-сервере</span><span class="sxs-lookup"><span data-stu-id="68d02-127">To add an interface to the set of interfaces that are to be exposed as Web services, using the Web hosting mode</span></span>  
  
- <span data-ttu-id="68d02-128">Выполните программу ComSvcConfig с параметрами `/install` и `/hosting:was`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-128">Run ComSvcConfig using the `/install` option and the `/hosting:was` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     <span data-ttu-id="68d02-129">Эта команда добавляет интерфейс `IStockLevels` компонента `ItemInventory.Warehouse` (из приложения COM+ OnlineWarehouse) в набор интерфейсов, предоставляемых как веб-службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-129">The command adds the `IStockLevels` interface on the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="68d02-130">Служба размещается на веб-сервере в виртуальном каталоге OnlineWarehouse службы IIS, а не COM+, а потому приложение включается автоматически по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="68d02-130">The service is Web hosted in the OnlineWarehouse virtual directory of IIS rather than in COM+, and thus the application is automatically activated as required.</span></span>  
  
     <span data-ttu-id="68d02-131">Чтобы воспользоваться конфигурацией с внутрипроцессным размещением на веб-сервере, приложение COM+ необходимо настроить для запуска как библиотечное приложение, а не серверное (с помощью консоли администрирования "Службы компонентов").</span><span class="sxs-lookup"><span data-stu-id="68d02-131">To use the Web-hosted in-process configuration, the COM+ application must be configured to run as a Library application rather than a Server application using the Component Services administration console.</span></span> <span data-ttu-id="68d02-132">Приложения, настроенные как серверные, используют стандартный режим размещения на веб-сервере, что приводит к переходам процесса при обработке каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="68d02-132">Applications configured as Server applications use the standard Web-hosted mode and incur a process hop to process each request.</span></span>  
  
     <span data-ttu-id="68d02-133">Параметр `/mex` добавляет дополнительную конечную точку службы обмена метаданными (MEX), использующую тот же транспорт, что и конечная точка службы приложения, для поддержки клиентов, которым требуется извлечь определение контракта от службы.</span><span class="sxs-lookup"><span data-stu-id="68d02-133">The `/mex` option adds an additional Metadata Exchange (MEX) service endpoint that uses the same transport as the application's service endpoint to support clients that want to retrieve a contract definition from the service.</span></span>  
  
### <a name="to-remove-a-web-service-for-a-specified-interface"></a><span data-ttu-id="68d02-134">Удаление веб-службы для указанного интерфейса</span><span class="sxs-lookup"><span data-stu-id="68d02-134">To remove a Web service for a specified interface</span></span>  
  
- <span data-ttu-id="68d02-135">Выполните программу ComSvcConfig с параметром `/uninstall`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-135">Run ComSvcConfig using the `/uninstall` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     <span data-ttu-id="68d02-136">Эта команда удаляет интерфейс `IFinances` компонента `ItemOrders.Financial` (из приложения COM+ OnlineStore).</span><span class="sxs-lookup"><span data-stu-id="68d02-136">The command removes the `IFinances` interface on the `ItemOrders.Financial` component (from the OnlineStore COM+ application).</span></span>  
  
### <a name="to-list-currently-exposed-interfaces"></a><span data-ttu-id="68d02-137">Вывод списка интерфейсов, предоставляемых в текущий момент</span><span class="sxs-lookup"><span data-stu-id="68d02-137">To list currently exposed interfaces</span></span>  
  
- <span data-ttu-id="68d02-138">Выполните программу ComSvcConfig с параметром `/list`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-138">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /list  
    ```  
  
     <span data-ttu-id="68d02-139">Эта команда выводит список предоставляемых в данный момент интерфейсов, а также соответствующий адрес и сведения о привязке, областью действия которых является локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="68d02-139">The command lists the currently exposed interfaces, along with the corresponding address and binding details, scoped to the local machine.</span></span>  
  
### <a name="to-list-specific-currently-exposed-interfaces"></a><span data-ttu-id="68d02-140">Вывод списка определенных интерфейсов, предоставляемых в текущий момент</span><span class="sxs-lookup"><span data-stu-id="68d02-140">To list specific currently exposed interfaces</span></span>  
  
- <span data-ttu-id="68d02-141">Выполните программу ComSvcConfig с параметром `/list`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-141">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     <span data-ttu-id="68d02-142">Эта команда выводит список предоставляемых в данный момент интерфейсов, размещенных в COM+, а также соответствующий адрес и сведения о привязке для приложения COM+ OnlineStore на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="68d02-142">The command lists currently exposed COM+-hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a><span data-ttu-id="68d02-143">Вывод справки о параметрах, используемых с программой</span><span class="sxs-lookup"><span data-stu-id="68d02-143">To display help on the options that can be used with the utility</span></span>  
  
- <span data-ttu-id="68d02-144">Запустите программу ComSvcConfig с параметром /?</span><span class="sxs-lookup"><span data-stu-id="68d02-144">Run ComSvcConfig using the /?</span></span> <span data-ttu-id="68d02-145">как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="68d02-145">option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68d02-146">См. также</span><span class="sxs-lookup"><span data-stu-id="68d02-146">See also</span></span>

- [<span data-ttu-id="68d02-147">Общие сведения об интеграции с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="68d02-147">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
