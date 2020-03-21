---
title: Пример федерации
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: 9ec462f88c0e3a039b7f288554be3e28f13ece08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144673"
---
# <a name="federation-sample"></a><span data-ttu-id="fe807-102">Пример федерации</span><span class="sxs-lookup"><span data-stu-id="fe807-102">Federation Sample</span></span>
<span data-ttu-id="fe807-103">В данном примере демонстрируется федеративная безопасность.</span><span class="sxs-lookup"><span data-stu-id="fe807-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="fe807-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="fe807-104">Sample Details</span></span>  
 <span data-ttu-id="fe807-105">Фонд связи Windows (WCF) обеспечивает поддержку развертывания федеративных архитектур безопасности через `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="fe807-105">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="fe807-106">Привязка `wsFederationHttpBinding` обеспечивает наличие безопасной и надежной привязки, которая поддерживает возможность взаимодействия. Данная привязка предполагает использование протокола HTTP в качестве базового транспортного механизма для взаимодействия типа "запрос-ответ" и текста/XML в качестве формата подключения для кодирования.</span><span class="sxs-lookup"><span data-stu-id="fe807-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="fe807-107">Для получения дополнительной информации о Федерации в WCF, [см.](../../../../docs/framework/wcf/feature-details/federation.md)</span><span class="sxs-lookup"><span data-stu-id="fe807-107">For more information about Federation in WCF, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="fe807-108">Сценарий состоит из 4 частей:</span><span class="sxs-lookup"><span data-stu-id="fe807-108">The scenario is made up of 4 pieces:</span></span>  
  
- <span data-ttu-id="fe807-109">служба BookStore;</span><span class="sxs-lookup"><span data-stu-id="fe807-109">BookStore service</span></span>  
  
- <span data-ttu-id="fe807-110">служба маркеров безопасности BookStore;</span><span class="sxs-lookup"><span data-stu-id="fe807-110">BookStore STS</span></span>  
  
- <span data-ttu-id="fe807-111">служба маркеров безопасности HomeRealm;</span><span class="sxs-lookup"><span data-stu-id="fe807-111">HomeRealm STS</span></span>  
  
- <span data-ttu-id="fe807-112">клиент BookStore.</span><span class="sxs-lookup"><span data-stu-id="fe807-112">BookStore Client</span></span>  
  
 <span data-ttu-id="fe807-113">Служба BookStore поддерживает две операции: `BrowseBooks` и `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="fe807-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="fe807-114">Служба позволяет выполнять анонимный доступ к операции `BrowseBooks`, но требует доступ с проверкой подлинности к операции `BuyBooks` .</span><span class="sxs-lookup"><span data-stu-id="fe807-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="fe807-115">Проверка подлинности принимает форму маркера, выданного службой маркеров безопасности BookStore.</span><span class="sxs-lookup"><span data-stu-id="fe807-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="fe807-116">Файл конфигурации службы BookStore указывает клиентам на службу маркеров безопасности BookStore с помощью `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="fe807-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="fe807-117">Затем служба маркеров безопасности BookStore требует, чтобы проверка подлинности клиента выполнялась с помощью маркера, выданного службой маркеров безопасности HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="fe807-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="fe807-118">И снова файл конфигурации службы маркеров безопасности BookStore указывает клиентам на службу маркеров безопасности HomeRealm с помощью `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="fe807-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="fe807-119">Ниже приведена последовательность событий при получении доступа к операции `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="fe807-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1. <span data-ttu-id="fe807-120">Клиент проходит проверку подлинности в службе маркеров безопасности HomeRealm с использованием учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="fe807-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2. <span data-ttu-id="fe807-121">Служба маркеров безопасности HomeRealm выдает маркер, который может использоваться для проверки подлинности в службе маркеров безопасности BookStore.</span><span class="sxs-lookup"><span data-stu-id="fe807-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3. <span data-ttu-id="fe807-122">Клиент проходит проверку подлинности в службе маркеров безопасности BookStore с использованием маркера, выданного службой маркеров безопасности HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="fe807-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4. <span data-ttu-id="fe807-123">Служба маркеров безопасности BookStore выдает маркер, который может использоваться для проверки подлинности в службе BookStore.</span><span class="sxs-lookup"><span data-stu-id="fe807-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5. <span data-ttu-id="fe807-124">Клиент проходит проверку подлинности в службе BookStore с использованием маркера, выданного службой маркеров безопасности BookStore.</span><span class="sxs-lookup"><span data-stu-id="fe807-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6. <span data-ttu-id="fe807-125">Клиент получает доступ к операции `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="fe807-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="fe807-126">В приведенных ниже инструкциях описаны настройка и запуск данного образца.</span><span class="sxs-lookup"><span data-stu-id="fe807-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe807-127">Для выполнения этого образца необходимо иметь разрешение на запись в каталог **wwwroot.**</span><span class="sxs-lookup"><span data-stu-id="fe807-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fe807-128">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="fe807-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="fe807-129">Откройте окно командной строки SDK.</span><span class="sxs-lookup"><span data-stu-id="fe807-129">Open the SDK command window.</span></span> <span data-ttu-id="fe807-130">Выполните Setup.bat в пути образца.</span><span class="sxs-lookup"><span data-stu-id="fe807-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="fe807-131">При этом будут созданы требуемые для образца виртуальные каталоги и установлены необходимые сертификаты с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="fe807-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fe807-132">Пакетный файл Setup.bat предназначен для запуска из командной строки Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="fe807-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="fe807-133">Требуется, чтобы переменная среды MSSDK указывала на каталог, в котором установлен пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="fe807-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="fe807-134">Эта переменная среды автоматически устанавливается в командной строке Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="fe807-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="fe807-135">На Windows Vista необходимо убедиться, что совместимость управления IIS 6.0 установлена, поскольку в настройке используются скрипты администратора IIS.</span><span class="sxs-lookup"><span data-stu-id="fe807-135">On Windows Vista, you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="fe807-136">Запуск сценария настройки на Windows Vista требует привилегий администратора.</span><span class="sxs-lookup"><span data-stu-id="fe807-136">Running the set-up script on Windows Vista requires administrator privileges.</span></span>  
  
2. <span data-ttu-id="fe807-137">Open FederationSample.sln в визуальной студии и выберите **решение сборки** из меню **Сборка.**</span><span class="sxs-lookup"><span data-stu-id="fe807-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="fe807-138">При этом будут построены и развернуты в IIS общие файлы проекта, служба Bookstore, служба маркеров безопасности Bookstore, служба маркеров безопасности HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="fe807-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="fe807-139">Кроме того, при этом будет построено клиентское приложение Bookstore. Его исполняемый файл BookStoreClient.exe будет размещен в папке FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="fe807-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3. <span data-ttu-id="fe807-140">Дважды щелкните BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="fe807-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="fe807-141">Отобразится окно BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="fe807-141">The BookStoreClient window is displayed.</span></span>  
  
4. <span data-ttu-id="fe807-142">Вы можете просмотреть книги, доступные в книжном магазине, нажав **Просмотр книг**.</span><span class="sxs-lookup"><span data-stu-id="fe807-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5. <span data-ttu-id="fe807-143">Чтобы приобрести конкретную книгу, выберите книгу в списке и нажмите **Купить книгу**.</span><span class="sxs-lookup"><span data-stu-id="fe807-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="fe807-144">Приложение запустится и пройдет проверку подлинности с использованием проверки подлинности Windows со службой маркеров безопасности HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="fe807-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="fe807-145">Конфигурация данного примера позволяет пользователям приобретать книги, которые стоят 15 долларов США или меньше.</span><span class="sxs-lookup"><span data-stu-id="fe807-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="fe807-146">Попытка приобрести книгу, стоимость которой превышает 15 долларов США, приводит к тому, что клиент получает сообщение «Доступ запрещен» от службы Book Store.</span><span class="sxs-lookup"><span data-stu-id="fe807-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fe807-147">В данном примере кредитный лимит пользователя после покупки не обновляется.</span><span class="sxs-lookup"><span data-stu-id="fe807-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="fe807-148">Вы можете повторно приобрести книги на сумму в пределах пользовательского (фиксированного) кредитного лимита.</span><span class="sxs-lookup"><span data-stu-id="fe807-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="fe807-149">Очистка</span><span class="sxs-lookup"><span data-stu-id="fe807-149">To clean up</span></span>  
  
1. <span data-ttu-id="fe807-150">Запустите Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="fe807-150">Run Cleanup.bat.</span></span> <span data-ttu-id="fe807-151">При этом будут удалены виртуальные каталоги и сертификаты, созданные во время установки.</span><span class="sxs-lookup"><span data-stu-id="fe807-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fe807-152">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fe807-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fe807-153">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fe807-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="fe807-154">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="fe807-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fe807-155">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="fe807-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
