---
title: Практическое руководство. Обработка событий в приложениях веб-форм
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc1dee9377200e4c9fd575b8dcd00982db45f249
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317822"
---
# <a name="how-to-consume-events-in-a-web-forms-application"></a>Практическое руководство. Обработка событий в приложениях веб-форм
Распространенный сценарий в приложениях веб-форм ASP.NET — заполнение веб-страницы элементами управления и выполнение определенных действий в зависимости от того, какой элемент управления выбрал пользователь. Например, элемент управления <xref:System.Web.UI.WebControls.Button?displayProperty=nameWithType> вызывает событие, когда пользователь щелкает его на странице. При обработке события приложение может выполнить соответствующую логику приложения для этого нажатия кнопки.  
  
### <a name="to-handle-a-button-click-event-on-a-webpage"></a>Обработка события нажатия кнопки на веб-странице  
  
1. Создайте страницу веб-форм ASP.NET, содержащую элемент управления <xref:System.Web.UI.WebControls.Button>, значение `OnClick` которого равно имени метода, который будет определен на следующем шаге.  
  
    ```xml  
    <asp:Button ID="Button1" runat="server" Text="Click Me" OnClick="Button1_Click" />  
    ```  
  
2. Определите обработчик событий, который соответствует сигнатуре делегата события <xref:System.Web.UI.WebControls.Button.Click>, с именем, определенным для значения `OnClick`.  
  
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
  
     Событие <xref:System.Web.UI.WebControls.Button.Click> использует класс <xref:System.EventHandler> для типа делегата и класс <xref:System.EventArgs> для данных события. Платформа, на которой работает страница ASP.NET, автоматически формирует код, создающий экземпляр <xref:System.EventHandler>, и добавляет этот экземпляр делегата в событие <xref:System.Web.UI.WebControls.Button.Click> экземпляра <xref:System.Web.UI.WebControls.Button>.  
  
3. В метод обработчика событий, определенный на втором шаге, добавьте код для выполнения действий, которые должны быть выполнены при возникновении события.  
  
## <a name="see-also"></a>См. также

- [События](../../../docs/standard/events/index.md)
