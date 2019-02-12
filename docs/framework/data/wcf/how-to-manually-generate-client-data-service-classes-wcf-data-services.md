---
title: Как выполнить  Вручную создайте клиентские классы службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: d197088f94614aac007c0adc310500ae4609f757
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091660"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="f5bb9-102">Как выполнить  Вручную создайте клиентские классы службы данных (службы данных WCF)</span><span class="sxs-lookup"><span data-stu-id="f5bb9-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="f5bb9-103">Службы WCF Data Services интегрируется с Visual Studio, позволяя автоматически сформировать клиентские классы службы данных, при использовании **Add Service Reference** диалоговое окно, чтобы добавить ссылку на службу данных в проект Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="f5bb9-104">Дополнительные сведения см. в разделе [Как Добавьте ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5bb9-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="f5bb9-105">Эти же клиентские классы службы данных можно сформировать и вручную с помощью программы для формирования кода `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="f5bb9-106">Это средство, которое входит в состав службы данных WCF, формирует классы .NET Framework из определения службы данных.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="f5bb9-107">Она также может использоваться для формирования классов службы данных из файла концептуальной модели (CSDL) и из файла EDMX, представляющего модель Entity Framework в проекте Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="f5bb9-108">Пример в этом разделе создает клиентские классы службы данных на основе образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="f5bb9-109">Эта служба создается после завершения [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5bb9-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="f5bb9-110">Некоторые примеры в этом разделе требуют наличия файла концептуальной модели для модели Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="f5bb9-111">Дополнительные сведения см. в разделе [Как Использование EdmGen.exe для создания файлов модели и сопоставления](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="f5bb9-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="f5bb9-112">Некоторые примеры в этом разделе требуют наличия файла EDMX для модели Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="f5bb9-113">Дополнительные сведения см. в разделе [Обзор файла .edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f5bb9-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="f5bb9-114">Формирование классов C#, поддерживающих привязку данных</span><span class="sxs-lookup"><span data-stu-id="f5bb9-114">To generate C# classes that support data binding</span></span>

-   <span data-ttu-id="f5bb9-115">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="f5bb9-116">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="f5bb9-117">Формирование классов Visual Basic, поддерживающих привязку данных</span><span class="sxs-lookup"><span data-stu-id="f5bb9-117">To generate Visual Basic classes that support data binding</span></span>

-   <span data-ttu-id="f5bb9-118">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="f5bb9-119">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="f5bb9-120">Формирование классов C# на основе URI службы</span><span class="sxs-lookup"><span data-stu-id="f5bb9-120">To generate C# classes based on the service URI</span></span>

-   <span data-ttu-id="f5bb9-121">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="f5bb9-122">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="f5bb9-123">Формирование классов Visual Basic на основе URI службы</span><span class="sxs-lookup"><span data-stu-id="f5bb9-123">To generate Visual Basic classes based on the service URI</span></span>

-   <span data-ttu-id="f5bb9-124">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  <span data-ttu-id="f5bb9-125">Необходимо заменить значение, передаваемое в параметре `/uri:`, на URI имеющегося экземпляра образца службы данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="f5bb9-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="f5bb9-126">Формирование классов C# на основе файла концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="f5bb9-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="f5bb9-127">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="f5bb9-128">Формирование классов Visual Basic на основе файла концептуальной модели (CSDL)</span><span class="sxs-lookup"><span data-stu-id="f5bb9-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

-   <span data-ttu-id="f5bb9-129">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="f5bb9-130">Формирование классов C# на основе файла EDMX</span><span class="sxs-lookup"><span data-stu-id="f5bb9-130">To generate C# classes based on the .edmx file</span></span>

-   <span data-ttu-id="f5bb9-131">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="f5bb9-132">Формирование классов Visual Basic на основе файла EDMX</span><span class="sxs-lookup"><span data-stu-id="f5bb9-132">To generate Visual Basic classes based on the .edmx file</span></span>

-   <span data-ttu-id="f5bb9-133">Выполните в командной строке следующую команду (введя ее без разрывов строк):</span><span class="sxs-lookup"><span data-stu-id="f5bb9-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="f5bb9-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f5bb9-134">See also</span></span>

- [<span data-ttu-id="f5bb9-135">Создание библиотеки клиентов службы данных</span><span class="sxs-lookup"><span data-stu-id="f5bb9-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="f5bb9-136">Практическое руководство. Добавьте ссылку на службу данных</span><span class="sxs-lookup"><span data-stu-id="f5bb9-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="f5bb9-137">Служебная программа клиента службы данных WCF (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="f5bb9-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)