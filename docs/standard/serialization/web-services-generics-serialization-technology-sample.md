---
title: "Образец технологии сериализации универсальных шаблонов веб-служб"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e9d5ed7a1bb55803cd1df8c6c6c740e8facb306e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="91f37-102">Образец технологии сериализации универсальных шаблонов веб-служб</span><span class="sxs-lookup"><span data-stu-id="91f37-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="91f37-103">Скачать образец</span><span class="sxs-lookup"><span data-stu-id="91f37-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="91f37-104">В этом образце показано, как использовать сериализацию универсальных шаблонов в веб-службах ASP.NET и управлять ею.</span><span class="sxs-lookup"><span data-stu-id="91f37-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="91f37-105">Сборка образца с использованием Visual Studio</span><span class="sxs-lookup"><span data-stu-id="91f37-105">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="91f37-106">Откройте Visual Studio и выберите в меню **Файл** команду **Новый веб-сайт**.</span><span class="sxs-lookup"><span data-stu-id="91f37-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="91f37-107">В диалоговом окне **Новый веб-сайт** выберите в левой области язык программирования, а затем в правой области выберите элемент **Веб-служба ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="91f37-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3.  <span data-ttu-id="91f37-108">Нажмите кнопку **Обзор** и перейдите в подкаталог \CS\GenericsService.</span><span class="sxs-lookup"><span data-stu-id="91f37-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4.  <span data-ttu-id="91f37-109">Выберите файл Service.asmx, чтобы открыть его в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="91f37-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5.  <span data-ttu-id="91f37-110">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="91f37-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f37-111">Первые пять шагов в этом списке являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="91f37-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="91f37-112">Среда выполнения .NET Framework автоматически создает веб-службу, когда она запрашивается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="91f37-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91f37-113">Для построения образца необходимы следующие действия.</span><span class="sxs-lookup"><span data-stu-id="91f37-113">The following steps are required to build the sample.</span></span>  
  
1.  <span data-ttu-id="91f37-114">Откройте [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] и перейдите в подкаталог \CS.</span><span class="sxs-lookup"><span data-stu-id="91f37-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to the \CS subdirectory.</span></span>  
  
2.  <span data-ttu-id="91f37-115">Щелкните правой кнопкой мыши значок подкаталога GenericsService и выберите пункт **Общий доступ и безопасность**.</span><span class="sxs-lookup"><span data-stu-id="91f37-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3.  <span data-ttu-id="91f37-116">На вкладке **Общий доступ в Интернете** выберите вариант **Открыть общий доступ к этой папке**.</span><span class="sxs-lookup"><span data-stu-id="91f37-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91f37-117">Запишите имя виртуального каталога, указанное в области **Псевдонимы**. Оно понадобится для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="91f37-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="91f37-118">Сборка образца с использованием служб IIS</span><span class="sxs-lookup"><span data-stu-id="91f37-118">To build the sample using Internet Information Services</span></span>  
  
1.  <span data-ttu-id="91f37-119">Откройте оснастку управления **Службы IIS** и разверните узел **Веб-сайты**.</span><span class="sxs-lookup"><span data-stu-id="91f37-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2.  <span data-ttu-id="91f37-120">Левой кнопкой мыши щелкните **Веб-сайт по умолчанию**, выберите **Создать**, а затем — **Виртуальный каталог?**, чтобы создать **мастер создания виртуального каталога**.</span><span class="sxs-lookup"><span data-stu-id="91f37-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3.  <span data-ttu-id="91f37-121">Нажмите кнопку **Далее**, введите открытый псевдоним для виртуального каталога и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="91f37-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="91f37-122">Введите путь к каталогу, где сохранен образец (обычно это подкаталог \CS\GenericsService), и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="91f37-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="91f37-123">Нажмите кнопку **Далее**, чтобы завершить работу мастера.</span><span class="sxs-lookup"><span data-stu-id="91f37-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91f37-124">Запишите имя виртуального каталога, указанное в области **Псевдоним**. Оно понадобится для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="91f37-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="91f37-125">Выполнение образца</span><span class="sxs-lookup"><span data-stu-id="91f37-125">To run the sample</span></span>  
  
1.  <span data-ttu-id="91f37-126">Откройте окно браузера и выделите адресную строку.</span><span class="sxs-lookup"><span data-stu-id="91f37-126">Open a browser window and select its address bar.</span></span>  
  
2.  <span data-ttu-id="91f37-127">Введите **http://localhost/[виртуальный каталог]/Service.asmx**, где [виртуальный каталог] представляет виртуальный каталог, созданный во время построения образца.</span><span class="sxs-lookup"><span data-stu-id="91f37-127">Type **http://localhost/[virtual directory]/Service.asmx**, where [virtual directory] represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91f37-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="91f37-128">Remarks</span></span>  
 <span data-ttu-id="91f37-129">В образце выводится страница ASP.NET по умолчанию, которая содержит ссылки на определение веб-службы.</span><span class="sxs-lookup"><span data-stu-id="91f37-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="91f37-130">Отображаемые данные можно настроить вместе с изменением исходного кода веб-службы.</span><span class="sxs-lookup"><span data-stu-id="91f37-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="91f37-131">Дополнительные сведения см. в разделе [Отладка XML-веб-служб](http://msdn.microsoft.com/en-us/c606f3cb-4111-45b4-ae42-9300420fa16c).</span><span class="sxs-lookup"><span data-stu-id="91f37-131">For more information, see [Building XML Web Service Clients](http://msdn.microsoft.com/en-us/c606f3cb-4111-45b4-ae42-9300420fa16c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f37-132">См. также</span><span class="sxs-lookup"><span data-stu-id="91f37-132">See Also</span></span>  
 <xref:System.Collections.Generic>  
 <xref:System.Web.Services>  
 <xref:System.Xml.Serialization>  
 [<span data-ttu-id="91f37-133">Сериализация</span><span class="sxs-lookup"><span data-stu-id="91f37-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)  
 [<span data-ttu-id="91f37-134">Веб-службы XML, созданные с помощью ASP.NET, и клиенты веб-служб с поддержкой XML</span><span class="sxs-lookup"><span data-stu-id="91f37-134">XML Web Services Created Using ASP.NET and XML Web Service Clients</span></span>](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c)
