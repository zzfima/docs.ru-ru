---
title: Создание службы WCF с поддержкой AJAX и клиента ASP.NET в Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 1f5c9eb1750b0df28836f147d5b4be1b223bb52e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053684"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="aeadd-102">Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET, обращающегося к службе</span><span class="sxs-lookup"><span data-stu-id="aeadd-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>

<span data-ttu-id="aeadd-103">В этом разделе показано, как использовать Visual Studio для создания службы Windows Communication Foundation (WCF) с поддержкой AJAX и клиента ASP.NET, обращающегося к службе.</span><span class="sxs-lookup"><span data-stu-id="aeadd-103">This topic shows how to use Visual Studio to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span>

## <a name="create-an-aspnet-web-app"></a><span data-ttu-id="aeadd-104">Создание веб-приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="aeadd-104">Create an ASP.NET web app</span></span>

1. <span data-ttu-id="aeadd-105">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aeadd-105">Open Visual Studio.</span></span>

1. <span data-ttu-id="aeadd-106">В меню **файл** выберите пункт **создать** > **проект** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-106">From the **File** menu, select **New** > **Project**</span></span>

1. <span data-ttu-id="aeadd-107">В диалоговом окне **Новый проект** разверните категорию **установленные** >   > **C#визуальные** **веб-** узлы и выберите **ASP.NET веб-приложение (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-107">In the **New Project** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select **ASP.NET Web Application (.NET Framework)**.</span></span>

1. <span data-ttu-id="aeadd-108">Присвойте проекту имя **сандвичсервицес** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-108">Name the Project **SandwichServices** and click **OK**.</span></span>

1. <span data-ttu-id="aeadd-109">В диалоговом окне **новое веб-приложение ASP.NET** выберите **пусто** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-109">In the **New ASP.NET Web Application** dialog, select **Empty** and then select **OK**.</span></span>

   ![Диалоговое окно типа веб-приложения ASP.NET в Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a><span data-ttu-id="aeadd-111">Добавление веб-формы</span><span class="sxs-lookup"><span data-stu-id="aeadd-111">Add a web form</span></span>

1. <span data-ttu-id="aeadd-112">Щелкните правой кнопкой мыши проект сандвичсервицес в **Обозреватель решений** и выберите команду **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-112">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="aeadd-113">В диалоговом окне **Добавление нового элемента** разверните категорию **установленная** >   > **C#визуальная** **веб-** Категория, а затем выберите шаблон **веб-форма** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-113">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **Web Form** template.</span></span>

1. <span data-ttu-id="aeadd-114">Примите имя по умолчанию (**WebForm1**) и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-114">Accept the default name (**WebForm1**), and then select **Add**.</span></span>

   <span data-ttu-id="aeadd-115">В представлении **исходного кода** откроется *WebForm1. aspx* .</span><span class="sxs-lookup"><span data-stu-id="aeadd-115">*WebForm1.aspx* opens in **Source** view.</span></span>

1. <span data-ttu-id="aeadd-116">Добавьте следующую разметку внутри  **\<тела >** тегами:</span><span class="sxs-lookup"><span data-stu-id="aeadd-116">Add the following markup inside the **\<body>** tags:</span></span>

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a><span data-ttu-id="aeadd-117">Создание службы WCF с поддержкой AJAX</span><span class="sxs-lookup"><span data-stu-id="aeadd-117">Create an AJAX-enabled WCF service</span></span>

1. <span data-ttu-id="aeadd-118">Щелкните правой кнопкой мыши проект сандвичсервицес в **Обозреватель решений** и выберите команду **Добавить** > **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-118">Right-click the SandwichServices project in **Solution Explorer** and select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="aeadd-119">В диалоговом окне **Добавление нового элемента** разверните категорию **установленные** >   > **визуальные C#**  **веб-** узлы, а затем выберите шаблон **Служба WCF (с поддержкой AJAX)** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-119">In the **Add New Item** dialog, expand the **Installed** > **Visual C#** > **Web** category, and then select the **WCF Service (AJAX-enabled)** template.</span></span>

   ![Шаблон элемента службы WCF (с поддержкой AJAX) в Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. <span data-ttu-id="aeadd-121">Назовите службу **костсервице** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-121">Name the service **CostService** and then select **Add**.</span></span>

   <span data-ttu-id="aeadd-122">*CostService.svc.CS* откроется в редакторе.</span><span class="sxs-lookup"><span data-stu-id="aeadd-122">*CostService.svc.cs* opens in the editor.</span></span>

1. <span data-ttu-id="aeadd-123">Реализуйте операцию в службе.</span><span class="sxs-lookup"><span data-stu-id="aeadd-123">Implement the operation in the service.</span></span> <span data-ttu-id="aeadd-124">Добавьте следующий метод в класс Костсервице для вычисления стоимости количества бутерброды:</span><span class="sxs-lookup"><span data-stu-id="aeadd-124">Add the following method to the CostService class to calculate the cost of a quantity of sandwiches:</span></span>

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a><span data-ttu-id="aeadd-125">Настройка клиента для доступа к службе</span><span class="sxs-lookup"><span data-stu-id="aeadd-125">Configure the client to access the service</span></span>

1. <span data-ttu-id="aeadd-126">Откройте файл *WebForm1. aspx* и выберите представление **конструктора** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-126">Open the *WebForm1.aspx* file and select the **Design** view.</span></span>

2. <span data-ttu-id="aeadd-127">В меню **вид** выберите пункт **область элементов**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-127">From the **View** menu, select **Toolbox**.</span></span>

3. <span data-ttu-id="aeadd-128">Разверните узел **расширения AJAX** и перетащите **ScriptManager** на форму.</span><span class="sxs-lookup"><span data-stu-id="aeadd-128">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** onto the form.</span></span>

4. <span data-ttu-id="aeadd-129">В представлении **исходного** кода добавьте следующий код между  **\<тегами > ScriptManager** , чтобы указать путь к службе WCF:</span><span class="sxs-lookup"><span data-stu-id="aeadd-129">Back in the **Source** view, add the following code between the **\<ScriptManager>** tags to specify the path to the WCF service:</span></span>

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. <span data-ttu-id="aeadd-130">Добавьте код для функции `Calculate()`JavaScript.</span><span class="sxs-lookup"><span data-stu-id="aeadd-130">Add the code for the Javascript function `Calculate()`.</span></span> <span data-ttu-id="aeadd-131">Поместите следующий код в раздел **head** веб-формы:</span><span class="sxs-lookup"><span data-stu-id="aeadd-131">Place the following code in the **head** section of the web form:</span></span>

    ```html
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

   <span data-ttu-id="aeadd-132">Этот код вызывает метод Костсервице для вычисления цены на три бутерброды, а затем отображает результат в диапазоне с именем **аддитионресулт**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-132">This code calls the method of CostService to calculate the price for three sandwiches, and then displays the result in the span called **additionResult**.</span></span>

## <a name="run-the-program"></a><span data-ttu-id="aeadd-133">Запуск программы</span><span class="sxs-lookup"><span data-stu-id="aeadd-133">Run the program</span></span>

<span data-ttu-id="aeadd-134">Убедитесь, что в элементе *WebForm1. aspx* установлен фокус, а затем нажмите кнопку **запустить** , чтобы запустить веб-клиент.</span><span class="sxs-lookup"><span data-stu-id="aeadd-134">Make sure that *WebForm1.aspx* has focus, and then press **Start** button to launch the web client.</span></span> <span data-ttu-id="aeadd-135">Кнопка имеет зеленый треугольник и говорит нечто вроде **IIS Express (Microsoft ребр)** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-135">The button has a green triangle and says something like **IIS Express (Microsoft Edge)**.</span></span> <span data-ttu-id="aeadd-136">Можно также нажать клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="aeadd-136">Or, you can press **F5**.</span></span> <span data-ttu-id="aeadd-137">Чтобы создать ожидаемый результат "3,75", нажмите кнопку **Цена, равную 3 бутерброды** .</span><span class="sxs-lookup"><span data-stu-id="aeadd-137">Click the **Price of 3 sandwiches** button to generate the expected output of "3.75".</span></span>

## <a name="example-code"></a><span data-ttu-id="aeadd-138">пример кода</span><span class="sxs-lookup"><span data-stu-id="aeadd-138">Example code</span></span>

<span data-ttu-id="aeadd-139">Ниже приведен полный код в файле *CostService.svc.CS* :</span><span class="sxs-lookup"><span data-stu-id="aeadd-139">Following is the full code in the *CostService.svc.cs* file :</span></span>

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

<span data-ttu-id="aeadd-140">Ниже приведено полное содержимое страницы *WebForm1. aspx* :</span><span class="sxs-lookup"><span data-stu-id="aeadd-140">Following is the full contents of the *WebForm1.aspx* page:</span></span>

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
