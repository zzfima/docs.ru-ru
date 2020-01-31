---
title: Практическое руководство. Регистрация и настройка моникера службы
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: fc0b2d00bcc8e3b14c491446f16297c1036b783b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747092"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="0b61b-102">Практическое руководство. Регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="0b61b-102">How to: Register and Configure a Service Moniker</span></span>

<span data-ttu-id="0b61b-103">Перед использованием моникера службы Windows Communication Foundation (WCF) в приложении COM с типизированным контрактом необходимо зарегистрировать необходимые типы с атрибутами в COM и настроить приложение COM и моникер с требуемой привязкой. Настройка.</span><span class="sxs-lookup"><span data-stu-id="0b61b-103">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>

## <a name="register-the-required-attributed-types-with-com"></a><span data-ttu-id="0b61b-104">Регистрация необходимых типов с атрибутами в COM</span><span class="sxs-lookup"><span data-stu-id="0b61b-104">Register the required attributed types with COM</span></span>

1. <span data-ttu-id="0b61b-105">Используйте средство [служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для получения контракта метаданных из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="0b61b-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="0b61b-106">При этом создается исходный код для клиентской сборки WCF и файла конфигурации клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="0b61b-106">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>

2. <span data-ttu-id="0b61b-107">Убедитесь, что все типы в сборке имеют пометку `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="0b61b-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="0b61b-108">Для этого добавьте следующий атрибут в файл *AssemblyInfo.CS* в проекте Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b61b-108">To do so, add the following attribute to the *AssemblyInfo.cs* file in your Visual Studio project.</span></span>

    ```csharp
    [assembly: ComVisible(true)]
    ```

3. <span data-ttu-id="0b61b-109">Скомпилируйте управляемый клиент WCF как сборку со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="0b61b-109">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="0b61b-110">Для этого нужно подписать ее с помощью пары ключей шифрования.</span><span class="sxs-lookup"><span data-stu-id="0b61b-110">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="0b61b-111">Дополнительные сведения см. в разделе [Подпись сборки строгим именем](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="0b61b-111">For more information, see [Signing an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

4. <span data-ttu-id="0b61b-112">С помощью средства регистрации сборок (Regasm.exe) с параметром `-tlb` зарегистрируйте типы сборки в COM.</span><span class="sxs-lookup"><span data-stu-id="0b61b-112">Use the Assembly Registration (Regasm.exe) tool with the `-tlb` option to register the types in the assembly with COM.</span></span>

5. <span data-ttu-id="0b61b-113">Чтобы добавить сборку в глобальный кэш сборок, используйте средство глобального кэша сборок (Gacutil.exe).</span><span class="sxs-lookup"><span data-stu-id="0b61b-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b61b-114">Подписывание сборки и ее добавление в глобальный кэш сборок являются необязательными шагами, однако они могут упростить процесс загрузки сборки из правильного расположения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0b61b-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>

## <a name="configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="0b61b-115">Настройка COM-приложения и моникера с требуемой конфигурацией привязки</span><span class="sxs-lookup"><span data-stu-id="0b61b-115">Configure the COM application and the moniker with the required binding configuration</span></span>

- <span data-ttu-id="0b61b-116">Разместите определения привязок (создаваемые [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) в созданном файле конфигурации клиентского приложения) в файле конфигурации клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="0b61b-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="0b61b-117">Например, для исполняемого файла Visual Basic 6.0 с именем CallCenterClient.exe конфигурацию необходимо помещать в файл с именем CallCenterConfig.exe.config в том же каталоге, что и исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="0b61b-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="0b61b-118">Теперь клиентское приложение может использовать моникер.</span><span class="sxs-lookup"><span data-stu-id="0b61b-118">The client application can now use the moniker.</span></span> <span data-ttu-id="0b61b-119">Обратите внимание, что настройка привязки не требуется, если используется один из стандартных типов привязки, предоставляемых WCF.</span><span class="sxs-lookup"><span data-stu-id="0b61b-119">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>

     <span data-ttu-id="0b61b-120">Регистрируется следующий тип.</span><span class="sxs-lookup"><span data-stu-id="0b61b-120">The following type is registered.</span></span>

    ```csharp
    using System.ServiceModel;

    [ServiceContract]
    public interface IMathService
    {
        [OperationContract]
        public int Add(int x, int y);
        [OperationContract]
        public int Subtract(int x, int y);
    }
    ```

     <span data-ttu-id="0b61b-121">Доступ к приложению предоставляется через следующую привязку `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="0b61b-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="0b61b-122">Для заданного типа и конфигурации приложения используются следующие примеры строк моникера.</span><span class="sxs-lookup"><span data-stu-id="0b61b-122">For the given type and application configuration, the following example moniker strings are used.</span></span>

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1
    ```

     <span data-ttu-id="0b61b-123">или</span><span class="sxs-lookup"><span data-stu-id="0b61b-123">or</span></span>

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}
    ```

     <span data-ttu-id="0b61b-124">Можно использовать любую из этих строк моникера из приложения Visual Basic 6.0 после добавления ссылки на сборку, содержащую типы `IMathService`, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="0b61b-124">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>

    ```vb
    Dim mathProxy As IMathService
    Dim result As Integer

    Set mathProxy = GetObject( _
            "service4:address=http://localhost/MathService, _
            binding=wsHttpBinding, _
            bindingConfiguration=Binding1")

    result = mathProxy.Add(3, 5)
    ```

     <span data-ttu-id="0b61b-125">В этом примере определение конфигурации привязки `Binding1` хранится в соответствующем именованном файле конфигурации для клиентского приложения, например *vb6appname. exe. config*.</span><span class="sxs-lookup"><span data-stu-id="0b61b-125">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as *vb6appname.exe.config*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b61b-126">Аналогичный код можно использовать в C#, C++ или любом другом языке приложений .NET.</span><span class="sxs-lookup"><span data-stu-id="0b61b-126">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0b61b-127">Если моникер имеет неправильный формат или служба недоступна, вызов `GetObject` возвращает ошибку "Недопустимый синтаксис".</span><span class="sxs-lookup"><span data-stu-id="0b61b-127">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="0b61b-128">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="0b61b-128">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>

     <span data-ttu-id="0b61b-129">Хотя в этом разделе основное внимание уделяется использованию моникера службы из кода Visual Basic 6,0, можно использовать моникер службы на других языках.</span><span class="sxs-lookup"><span data-stu-id="0b61b-129">Although this topic focuses on using the service moniker from Visual Basic 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="0b61b-130">При использовании моникера из кода C++ сбоку, созданную с помощью средства Svcutil.exe, необходимо импортировать с атрибутом "no_namespace named_guids raw_interfaces_only", как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0b61b-130">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>

    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids
    ```

     <span data-ttu-id="0b61b-131">При этом изменяются определения импортированного интерфейса, чтобы все методы возвращали `HResult`.</span><span class="sxs-lookup"><span data-stu-id="0b61b-131">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="0b61b-132">Все остальные возвращаемые значения преобразуются в выходные параметры.</span><span class="sxs-lookup"><span data-stu-id="0b61b-132">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="0b61b-133">Общий процесс выполнения методов остается прежним.</span><span class="sxs-lookup"><span data-stu-id="0b61b-133">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="0b61b-134">Это позволяет определить причину исключения при вызове метода в прокси.</span><span class="sxs-lookup"><span data-stu-id="0b61b-134">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="0b61b-135">Эта функция доступна только в коде C++.</span><span class="sxs-lookup"><span data-stu-id="0b61b-135">This functionality is only available from C++ code.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b61b-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="0b61b-136">See also</span></span>

- [<span data-ttu-id="0b61b-137">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0b61b-137">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
