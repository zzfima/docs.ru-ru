---
title: Создать службу WCF с поддержкой AJAX и клиента ASP.NET в Visual Studio
ms.date: 08/17/2018
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 954ee0409f370c3fa28814a70d51334fd75f7b79
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46528844"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET для обращения к службе

В этом разделе показано, как использовать Visual Studio для создания службы с поддержкой AJAX Windows Communication Foundation (WCF) и клиента ASP.NET, который обращается к службе.

## <a name="create-an-aspnet-web-app"></a>Создание веб-приложения ASP.NET

1. Запустите Visual Studio.

1. Из **файл** меню, выберите **New** > **проекта**

1. В **новый проект** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **веб-приложение ASP.NET (.NET Framework)**.

1. Назовите проект **SandwichServices** и нажмите кнопку **ОК**.

1. В **новое веб-приложение ASP.NET** диалоговом окне выберите **пустой** , а затем выберите **ОК**.

   ![ASP.NET web app тип диалогового окна в Visual Studio](media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Добавление веб-формы

1. Щелкните правой кнопкой мыши проект SandwichServices в **обозревателе решений** и выберите **добавить** > **новый элемент**.

1. В **Добавление нового элемента** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **веб-формы** шаблона.

1. Примите имя по умолчанию (**WebForm1**), а затем выберите **добавить**.

   *WebForm1.aspx* открывается в **источника** представления.

1. Добавьте следующую разметку внутри  **\<текст >** теги:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Создание службы WCF с поддержкой AJAX

1. Щелкните правой кнопкой мыши проект SandwichServices в **обозревателе решений** и выберите **добавить** > **новый элемент**.

1. В **Добавление нового элемента** диалоговом окне разверните **установленные** > **Visual C#** > **Web** категории, а затем Выберите **службы WCF (с поддержкой AJAX)** шаблона.

   ![Шаблон (с поддержкой AJAX) элемента службы WCF в Visual Studio](media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Назовите службу **CostService** , а затем выберите **добавить**.

   *CostService.svc.cs* откроется в редакторе.

1. Реализация операции службы. Добавьте следующий метод к классу CostService для расчета стоимости количества сандвича:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Настройка клиента для доступа к службе

1. Откройте *WebForm1.aspx* файл и выберите **разработки** представления.

2. Из **представление** меню, выберите **элементов**.

3. Разверните **расширения AJAX** узел и перетащите **ScriptManager** на форму.

4. Вернитесь в **источника** Просмотр, добавьте следующий код между  **\<ScriptManager >** теги, чтобы указать путь к службе WCF:

    ```html
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

1. Добавьте код для функции Javascript `Calculate()`. Поместите следующий код в **head** раздел веб-формы:

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

   Этот код вызывает метод CostService для расчета цены за три сандвича и отображает результат в диапазон, который называется **additionResult**.

## <a name="run-the-program"></a>Запуск программы

Убедитесь, что *WebForm1.aspx* имеет фокус и нажмите клавишу **запустить** кнопку для запуска веб-клиента. Кнопка имеет зеленый треугольник и говорит нечто вроде **IIS Express (Microsoft Edge)**. Или можно нажать клавишу **F5**. Нажмите кнопку **цены 3 сандвича** кнопку, чтобы создать ожидаемый результат «3,75».

## <a name="example-code"></a>пример кода

Ниже приведен полный код в *CostService.svc.cs* файла:

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

Ниже приведен полный набор *WebForm1.aspx* страницы:

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
