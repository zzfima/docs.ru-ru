---
title: "Практическое руководство. Прием событий в приложениях Web Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "события [платформа .NET Framework], веб-формы"
  - "элементы управления веб-форм и события"
  - "обработчики событий [платформа .NET Framework], веб-формы"
  - "события [платформа .NET Framework], использование"
  - "веб-формы, обработка событий"
ms.assetid: 73bf8638-c4ec-4069-b0bb-a1dc79b92e32
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Прием событий в приложениях Web Forms
Распространенным сценарием в приложениях ASP.NET Web Forms является заполнение веб\-страницы элементами управления и последующее выполнение определенных действий в зависимости от того, какой элемент управления выбрал пользователь.  К примеру, когда пользователь нажимает элемент управления <xref:System.Web.UI.WebControls.Button?displayProperty=fullName>, расположенный на веб\-странице, создается событие.  При обработке события приложение может выполнить соответствующую логику приложения после нажатия кнопки.  
  
### Обработка события нажатия кнопки на веб\-странице  
  
1.  Создайте страницу ASP.NET Web Forms, содержащую элемент управления <xref:System.Web.UI.WebControls.Button> со значением `OnClick`, равным имени метода, который будет определен на следующем шаге.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2.  Определите обработчик событий, который соответствует сигнатуре делегата события <xref:System.Web.UI.WebControls.Button.Click> с именем, которое вы определили для значения `OnClick`.  
  
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
  
     Событие <xref:System.Web.UI.WebControls.Button.Click> использует класс <xref:System.EventHandler> для типа делегата и класс <xref:System.EventArgs> – для данных события.  Платформа, на которой работает страница ASP.NET, генерирует код, создающий экземпляр <xref:System.EventHandler>, и добавляет этот экземпляр делегата в событие <xref:System.Web.UI.WebControls.Button.Click> экземпляра <xref:System.Web.UI.WebControls.Button>.  
  
3.  В метод обработчика событий, определенный на втором шаге, добавьте код для выполнения каких\-либо действий, которые должны быть выполнены при возникновении события.  
  
## См. также  
 [События](../../../docs/standard/events/index.md)