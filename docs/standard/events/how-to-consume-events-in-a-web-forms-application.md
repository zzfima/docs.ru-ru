---
title: Практическое руководство. Прием событий в приложениях Web Forms
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [.NET Framework], Web Forms
- Web Forms controls, and events
- event handlers [.NET Framework], Web Forms
- events [.NET Framework], consuming
- Web Forms, event handling
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
ms.openlocfilehash: 1f95fd0dcc12f2d4e47ee07e1e6bb15d91000f0f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124787"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a><span data-ttu-id="185e7-102">Практическое руководство. Прием событий в приложениях Web Forms</span><span class="sxs-lookup"><span data-stu-id="185e7-102">How to: Consume Events in a Web Forms Application</span></span>
<span data-ttu-id="185e7-103">Распространенный сценарий в приложениях веб-форм ASP.NET — заполнение веб-страницы элементами управления и выполнение определенных действий в зависимости от того, какой элемент управления выбрал пользователь.</span><span class="sxs-lookup"><span data-stu-id="185e7-103">A common scenario in ASP.NET Web Forms applications is to populate a webpage with controls, and then perform a specific action based on which control the user clicks.</span></span> <span data-ttu-id="185e7-104">Например, элемент управления <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> вызывает событие, когда пользователь щелкает его на странице.</span><span class="sxs-lookup"><span data-stu-id="185e7-104">For example, a <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> control raises an event when the user clicks it in the webpage.</span></span> <span data-ttu-id="185e7-105">При обработке события приложение может выполнить соответствующую логику приложения для этого нажатия кнопки.</span><span class="sxs-lookup"><span data-stu-id="185e7-105">By handling the event, your application can perform the appropriate application logic for that button click.</span></span>  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a><span data-ttu-id="185e7-106">Обработка события нажатия кнопки на веб-странице</span><span class="sxs-lookup"><span data-stu-id="185e7-106">To handle a button click event on a webpage</span></span>  
  
1. <span data-ttu-id="185e7-107">Создайте страницу веб-форм ASP.NET, содержащую элемент управления <xref:System.Web.UI.WebControls.Button>, значение `OnClick` которого равно имени метода, который будет определен на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="185e7-107">Create a ASP.NET Web Forms page (webpage) that has a <xref:System.Web.UI.WebControls.Button> control with the `OnClick` value set to the name of method that you will define in the next step.</span></span>  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. <span data-ttu-id="185e7-108">Определите обработчик событий, который соответствует сигнатуре делегата события <xref:System.Web.UI.WebControls.Button.Click>, с именем, определенным для значения `OnClick`.</span><span class="sxs-lookup"><span data-stu-id="185e7-108">Define an event handler that matches the <xref:System.Web.UI.WebControls.Button.Click> event delegate signature and that has the name you defined for the `OnClick` value.</span></span>  
  
    ```csharp  
    protected void Button1_Click(object sender, EventArgs e)  
    {  
        // perform action  
    }  
    ```  
  
    ```vb  
    Protected Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' perform action  
    End Sub  
    ```  
  
     <span data-ttu-id="185e7-109">Событие <xref:System.Web.UI.WebControls.Button.Click> использует класс <xref:System.EventHandler> для типа делегата и класс <xref:System.EventArgs> для данных события.</span><span class="sxs-lookup"><span data-stu-id="185e7-109">The <xref:System.Web.UI.WebControls.Button.Click> event uses the <xref:System.EventHandler> class for the delegate type and the <xref:System.EventArgs> class for the event data.</span></span> <span data-ttu-id="185e7-110">Платформа, на которой работает страница ASP.NET, автоматически формирует код, создающий экземпляр <xref:System.EventHandler>, и добавляет этот экземпляр делегата в событие <xref:System.Web.UI.WebControls.Button.Click> экземпляра <xref:System.Web.UI.WebControls.Button>.</span><span class="sxs-lookup"><span data-stu-id="185e7-110">The ASP.NET page framework automatically generates code that creates an instance of <xref:System.EventHandler> and adds this delegate instance to the <xref:System.Web.UI.WebControls.Button.Click> event of the <xref:System.Web.UI.WebControls.Button> instance.</span></span>  
  
3. <span data-ttu-id="185e7-111">В метод обработчика событий, определенный на втором шаге, добавьте код для выполнения действий, которые должны быть выполнены при возникновении события.</span><span class="sxs-lookup"><span data-stu-id="185e7-111">In the event handler method that you defined in step 2, add code to perform any actions that are required when the event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185e7-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="185e7-112">See also</span></span>

- [<span data-ttu-id="185e7-113">События</span><span class="sxs-lookup"><span data-stu-id="185e7-113">Events</span></span>](../../../docs/standard/events/index.md)
