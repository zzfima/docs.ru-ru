---
title: Создать службу WCF с поддержкой AJAX и клиента ASP.NET в Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009314"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="1fc6b-102">Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET для обращения к службе</span><span class="sxs-lookup"><span data-stu-id="1fc6b-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="1fc6b-103">В этом разделе показано, как использовать Visual Studio для создания службы с поддержкой AJAX Windows Communication Foundation (WCF) и клиента ASP.NET, который обращается к службе.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="1fc6b-104">Создание веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1fc6b-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="1fc6b-105">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="1fc6b-106">Из **файл** меню, выберите **New** > **проекта**</span><span class="sxs-lookup"><span data-stu-id="1fc6b-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="1fc6b-107">В **новый проект** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **веб-приложение ASP.NET (.NET Framework)**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="1fc6b-108">Назовите проект **SandwichServices** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="1fc6b-109">В **новое веб-приложение ASP.NET** диалоговом окне выберите **пустой** , а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![ASP.NET web app тип диалогового окна в Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="1fc6b-111">Добавление веб-формы</span><span class="sxs-lookup"><span data-stu-id="1fc6b-111">Add a web form</span></span>

1. <span data-ttu-id="1fc6b-112">Щелкните правой кнопкой мыши проект SandwichServices в **обозревателе решений** и выберите **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="1fc6b-113">В **Добавление нового элемента** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **веб-формы** шаблона.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="1fc6b-114">Примите имя по умолчанию (**WebForm1**), а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="1fc6b-115">*WebForm1.aspx* открывается в **источника** представления.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="1fc6b-116">Добавьте следующую разметку внутри  **\<текст >** теги:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="1fc6b-117">Создание службы WCF с поддержкой AJAX</span><span class="sxs-lookup"><span data-stu-id="1fc6b-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="1fc6b-118">Щелкните правой кнопкой мыши проект SandwichServices в **обозревателе решений** и выберите **добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="1fc6b-119">В **Добавление нового элемента** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **службы WCF (с поддержкой AJAX)** шаблона.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Шаблон (с поддержкой AJAX) элемента службы WCF в Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="1fc6b-121">Назовите службу **CostService** , а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="1fc6b-122">*CostService.svc.cs* откроется в редакторе.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="1fc6b-123">Реализация операции службы.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-123">Implement the operation in the service.</span></span> <span data-ttu-id="1fc6b-124">Добавьте следующий метод к классу CostService для расчета стоимости количества сандвича:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="1fc6b-125">Настройка клиента для доступа к службе</span><span class="sxs-lookup"><span data-stu-id="1fc6b-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="1fc6b-126">Откройте *WebForm1.aspx* файл и выберите **разработки** представления.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="1fc6b-127">Из **представление** меню, выберите **элементов**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="1fc6b-128">Разверните **расширения AJAX** узел и перетащите **ScriptManager** на форму.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="1fc6b-129">Вернитесь в **источника** Просмотр, добавьте следующий код между  **\<ScriptManager >** теги, чтобы указать путь к службе WCF:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. <span data-ttu-id="1fc6b-130">Добавьте код для функции Javascript `Calculate()`.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="1fc6b-131">Поместите следующий код в **head** раздел веб-формы:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-131">Place the following code in the **head** section of the web form:</span></span>

    ```javascript
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
    ```

   <span data-ttu-id="1fc6b-132">Этот код вызывает метод CostService для расчета цены за три сандвича и отображает результат в диапазон, который называется **additionResult**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="1fc6b-133">Запуск программы</span><span class="sxs-lookup"><span data-stu-id="1fc6b-133">Run the program</span></span>

<span data-ttu-id="1fc6b-134">Убедитесь, что *WebForm1.aspx* имеет фокус и нажмите клавишу **запустить** кнопку для запуска веб-клиента.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="1fc6b-135">Кнопка имеет зеленый треугольник и говорит нечто вроде **IIS Express (Microsoft Edge)**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="1fc6b-136">Или можно нажать клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="1fc6b-136">Or, you can press **F5**.</span></span> <span data-ttu-id="1fc6b-137">Нажмите кнопку **цены 3 сандвича** кнопку, чтобы создать ожидаемый результат «3,75».</span><span class="sxs-lookup"><span data-stu-id="1fc6b-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="1fc6b-138">пример кода</span><span class="sxs-lookup"><span data-stu-id="1fc6b-138">Example code</span></span>

<span data-ttu-id="1fc6b-139">Ниже приведен полный код в *CostService.svc.cs* файла:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

```csharp
using System.ServiceModel;
using System.ServiceModel.Activation;

namespace SandwichServices
{
    [ServiceContract(Namespace = "")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class CostService
    {
        [OperationContract]
        public double CostOfSandwiches(int quantity)
        {
            return 1.25 * quantity;
        }
    }
}
```

<span data-ttu-id="1fc6b-140">Ниже приведен полный набор *WebForm1.aspx* страницы:</span><span class="sxs-lookup"><span data-stu-id="1fc6b-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

```aspx-csharp
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="SandwichServices.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
    <script type="text/javascript">

        function Calculate() {
            CostService.CostOfSandwiches(3, onSuccess);
        }

        function onSuccess(result) {
            var myres = $get("additionResult");
            myres.innerHTML = result;
        }

    </script>
</head>
<body>
    <form id="form1" runat="server">
        <div>
        </div>
        <asp:ScriptManager ID="ScriptManager1" runat="server">
            <Services>
                <asp:ServiceReference Path="~/CostService.svc" />
            </Services>
        </asp:ScriptManager>

        <input type="button" value="Price of 3 sandwiches" onclick="Calculate()" />
        <br />
        <span id="additionResult"></span>
    </form>
</body>
</html>
```
