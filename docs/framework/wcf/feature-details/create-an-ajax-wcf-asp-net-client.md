---
title: "Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET для обращения к службе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a45a186b0d281976f3d6ad554d75742ba0f1cd50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="89661-102">Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET для обращения к службе</span><span class="sxs-lookup"><span data-stu-id="89661-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="89661-103">В этом разделе показано, как использовать Visual Studio 2008 для создания службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с поддержкой AJAX и клиента ASP.NET, который к ней обращается.</span><span class="sxs-lookup"><span data-stu-id="89661-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="89661-104">Коды для службы и для клиента содержатся в разделе «Пример», который следует за разделом «Процедуры», в котором описаны шаги их создания.</span><span class="sxs-lookup"><span data-stu-id="89661-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="89661-105">Создание клиентского приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="89661-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="89661-106">Откройте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89661-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="89661-107">Из **файл** последовательно выберите пункты **New**, затем **проекта**, затем **Web**и выберите **веб-приложение ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="89661-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="89661-108">Назовите проект `SandwichServices` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89661-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="89661-109">Создание службы WCF с поддержкой AJAX</span><span class="sxs-lookup"><span data-stu-id="89661-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="89661-110">Щелкните правой кнопкой мыши `SandwichServices` проекта в **обозревателе решений** и выберите **добавить**, затем **новый элемент**, а затем **служба WCF с поддержкой AJAX** .</span><span class="sxs-lookup"><span data-stu-id="89661-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="89661-111">Имя службы `CostService` в **имя** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="89661-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="89661-112">Откройте файл CostService.svc.cs.</span><span class="sxs-lookup"><span data-stu-id="89661-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="89661-113">Укажите `Namespace` для <xref:System.ServiceModel.ServiceContractAttribute> как `SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="89661-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  <span data-ttu-id="89661-114">Реализация операций службы.</span><span class="sxs-lookup"><span data-stu-id="89661-114">Implement the operations in the service.</span></span> <span data-ttu-id="89661-115">Добавьте <xref:System.ServiceModel.OperationContractAttribute> в каждую операцию для указания, что они являются частью контракта.</span><span class="sxs-lookup"><span data-stu-id="89661-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="89661-116">В следующем примере реализован метод, который возвращает стоимость заданного числа сандвичей.</span><span class="sxs-lookup"><span data-stu-id="89661-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="89661-117">Настройка клиента для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="89661-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="89661-118">Откройте страницу Default.aspx и выберите **разработки** представления.</span><span class="sxs-lookup"><span data-stu-id="89661-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="89661-119">Из **представление** последовательно выберите пункты **элементов**.</span><span class="sxs-lookup"><span data-stu-id="89661-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="89661-120">Разверните **расширения AJAX** узла и перетащите **ScriptManager** на страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="89661-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="89661-121">Щелкните правой кнопкой мыши **ScriptManager** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="89661-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="89661-122">Разверните **службы** коллекции в **свойства** чтобы открыть **редактор коллекции ServiceReference** окна.</span><span class="sxs-lookup"><span data-stu-id="89661-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="89661-123">Нажмите кнопку **добавить**, укажите `CostService.svc` как **путь** и нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="89661-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="89661-124">Разверните **HTML** узел в **элементов** и перетащите **Input (Button)** на страницу Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="89661-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="89661-125">Щелкните правой кнопкой мыши **кнопку** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="89661-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="89661-126">Изменение **значение** на `Price for 3 Sandwiches`.</span><span class="sxs-lookup"><span data-stu-id="89661-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="89661-127">Дважды щелкните **кнопку** для доступа к коду JavaScript.</span><span class="sxs-lookup"><span data-stu-id="89661-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="89661-128">Передайте следующий код JavaScript в <`script`> элемент.</span><span class="sxs-lookup"><span data-stu-id="89661-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="89661-129">Доступ к службе из клиента</span><span class="sxs-lookup"><span data-stu-id="89661-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="89661-130">Используйте сочетание клавиш Ctrl+F5 для запуска службы и веб-клиента.</span><span class="sxs-lookup"><span data-stu-id="89661-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="89661-131">Нажмите кнопку **цена за 3 Жареных Сандвича** кнопку, чтобы создать ожидаемый результат «3,75».</span><span class="sxs-lookup"><span data-stu-id="89661-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="89661-132">Пример</span><span class="sxs-lookup"><span data-stu-id="89661-132">Example</span></span>  
 <span data-ttu-id="89661-133">Этот пример содержит код службы, содержащийся в файле WCFService.svc.cs, и код клиента, содержащийся в файле Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="89661-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     
