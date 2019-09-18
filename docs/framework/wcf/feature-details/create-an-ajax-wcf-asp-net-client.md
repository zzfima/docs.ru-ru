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
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>Практическое руководство. Создание службы WCF с поддержкой AJAX и клиента ASP.NET, обращающегося к службе

В этом разделе показано, как использовать Visual Studio для создания службы Windows Communication Foundation (WCF) с поддержкой AJAX и клиента ASP.NET, обращающегося к службе.

## <a name="create-an-aspnet-web-app"></a>Создание веб-приложения ASP.NET

1. Запустите Visual Studio.

1. В меню **файл** выберите пункт **создать** > **проект** .

1. В диалоговом окне **Новый проект** разверните категорию **установленные** >   > **C#визуальные** **веб-** узлы и выберите **ASP.NET веб-приложение (.NET Framework)** .

1. Присвойте проекту имя **сандвичсервицес** и нажмите кнопку **ОК**.

1. В диалоговом окне **новое веб-приложение ASP.NET** выберите **пусто** и нажмите кнопку **ОК**.

   ![Диалоговое окно типа веб-приложения ASP.NET в Visual Studio](./media/create-an-ajax-wcf-asp-net-client/new-asp-net-web-app-type.png)

## <a name="add-a-web-form"></a>Добавление веб-формы

1. Щелкните правой кнопкой мыши проект сандвичсервицес в **Обозреватель решений** и выберите команду **Добавить** > **новый элемент**.

1. В диалоговом окне **Добавление нового элемента** разверните категорию **установленная** >   > **C#визуальная** **веб-** Категория, а затем выберите шаблон **веб-форма** .

1. Примите имя по умолчанию (**WebForm1**) и нажмите кнопку **Добавить**.

   В представлении **исходного кода** откроется *WebForm1. aspx* .

1. Добавьте следующую разметку внутри  **\<тела >** тегами:

   ```html
   <input type="button" value="Price of 3 sandwiches" onclick="Calculate()"/>
   <br />
   <span id="additionResult"></span>
   ```

## <a name="create-an-ajax-enabled-wcf-service"></a>Создание службы WCF с поддержкой AJAX

1. Щелкните правой кнопкой мыши проект сандвичсервицес в **Обозреватель решений** и выберите команду **Добавить** > **новый элемент**.

1. В диалоговом окне **Добавление нового элемента** разверните категорию **установленные** >   > **визуальные C#**  **веб-** узлы, а затем выберите шаблон **Служба WCF (с поддержкой AJAX)** .

   ![Шаблон элемента службы WCF (с поддержкой AJAX) в Visual Studio](./media/create-an-ajax-wcf-asp-net-client/add-wcf-service.png)

1. Назовите службу **костсервице** и нажмите кнопку **Добавить**.

   *CostService.svc.CS* откроется в редакторе.

1. Реализуйте операцию в службе. Добавьте следующий метод в класс Костсервице для вычисления стоимости количества бутерброды:

    ```csharp
    [OperationContract]
    public double CostOfSandwiches(int quantity)
    {
        return 1.25 * quantity;
    }
    ```

## <a name="configure-the-client-to-access-the-service"></a>Настройка клиента для доступа к службе

1. Откройте файл *WebForm1. aspx* и выберите представление **конструктора** .

2. В меню **вид** выберите пункт **область элементов**.

3. Разверните узел **расширения AJAX** и перетащите **ScriptManager** на форму.

4. В представлении **исходного** кода добавьте следующий код между  **\<тегами > ScriptManager** , чтобы указать путь к службе WCF:

    ```xml
    <Services>
       <asp:ServiceReference Path="~/CostService.svc" />
    </Services>
    ```

5. Добавьте код для функции `Calculate()`JavaScript. Поместите следующий код в раздел **head** веб-формы:

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

   Этот код вызывает метод Костсервице для вычисления цены на три бутерброды, а затем отображает результат в диапазоне с именем **аддитионресулт**.

## <a name="run-the-program"></a>Запуск программы

Убедитесь, что в элементе *WebForm1. aspx* установлен фокус, а затем нажмите кнопку **запустить** , чтобы запустить веб-клиент. Кнопка имеет зеленый треугольник и говорит нечто вроде **IIS Express (Microsoft ребр)** . Можно также нажать клавишу **F5**. Чтобы создать ожидаемый результат "3,75", нажмите кнопку **Цена, равную 3 бутерброды** .

## <a name="example-code"></a>пример кода

Ниже приведен полный код в файле *CostService.svc.CS* :

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

Ниже приведено полное содержимое страницы *WebForm1. aspx* :

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
