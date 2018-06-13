---
title: Практическое руководство. Создание клиентских классов служб данных вручную (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 24d19f10e025b765cfc7df73ba80d223fbfa8074
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358998"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="d38bd-102">Практическое руководство. Создание клиентских классов служб данных вручную (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="d38bd-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="d38bd-103"> интегрируется с Visual Studio, чтобы можно было автоматически сформировать клиентские классы службы данных при использовании **добавить ссылку на службу** диалогового окна для добавления ссылки на службу данных в проект Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d38bd-103"> integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="d38bd-104">Дополнительные сведения см. в разделе [как: Добавление ссылки на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d38bd-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="d38bd-105">Эти же клиентские классы службы данных можно сформировать и вручную с помощью программы для формирования кода `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="d38bd-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="d38bd-106">Программа поставляется в комплекте служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и формирует классы .NET Framework из определения службы данных.</span><span class="sxs-lookup"><span data-stu-id="d38bd-106">This tool, which is included with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="d38bd-107">Она также может использоваться для формирования классов службы данных из файла концептуальной модели (CSDL) и из файла EDMX, представляющего модель Entity Framework в проекте Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d38bd-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>  
  
 <span data-ttu-id="d38bd-108">Пример в этом разделе создает клиентские классы службы данных на основе образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="d38bd-109">Эта служба создается после завершения [краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d38bd-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="d38bd-110">Некоторые примеры в этом разделе требуют наличия файла концептуальной модели для модели Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="d38bd-111">Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="d38bd-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="d38bd-112">Некоторые примеры в этом разделе требуют наличия файла EDMX для модели Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="d38bd-113">Дополнительные сведения см. в разделе [.edmx Обзор файла](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="d38bd-113">For more information, see [.edmx File Overview](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="d38bd-114">Формирование классов C#, поддерживающих привязку данных</span><span class="sxs-lookup"><span data-stu-id="d38bd-114">To generate C# classes that support data binding</span></span>  
  
-   <span data-ttu-id="d38bd-115">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d38bd-116">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="d38bd-117">Формирование классов Visual Basic, поддерживающих привязку данных</span><span class="sxs-lookup"><span data-stu-id="d38bd-117">To generate Visual Basic classes that support data binding</span></span>  
  
-   <span data-ttu-id="d38bd-118">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-118">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d38bd-119">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="d38bd-120">Формирование классов C# на основе URI службы</span><span class="sxs-lookup"><span data-stu-id="d38bd-120">To generate C# classes based on the service URI</span></span>  
  
-   <span data-ttu-id="d38bd-121">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-121">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d38bd-122">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="d38bd-123">Формирование классов Visual Basic на основе URI службы</span><span class="sxs-lookup"><span data-stu-id="d38bd-123">To generate Visual Basic classes based on the service URI</span></span>  
  
-   <span data-ttu-id="d38bd-124">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-124">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d38bd-125">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="d38bd-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="d38bd-126">Формирование классов C# на основе файла концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="d38bd-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="d38bd-127">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-127">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="d38bd-128">Формирование классов Visual Basic на основе файла концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="d38bd-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="d38bd-129">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-129">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="d38bd-130">Формирование классов C# на основе файла EDMX</span><span class="sxs-lookup"><span data-stu-id="d38bd-130">To generate C# classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="d38bd-131">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-131">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="d38bd-132">Формирование классов Visual Basic на основе файла EDMX</span><span class="sxs-lookup"><span data-stu-id="d38bd-132">To generate Visual Basic classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="d38bd-133">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="d38bd-133">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d38bd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d38bd-134">See Also</span></span>  
 [<span data-ttu-id="d38bd-135">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="d38bd-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [<span data-ttu-id="d38bd-136">Практическое руководство. Добавление ссылки на службу данных</span><span class="sxs-lookup"><span data-stu-id="d38bd-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [<span data-ttu-id="d38bd-137">Служебная программа клиента службы данных WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="d38bd-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
