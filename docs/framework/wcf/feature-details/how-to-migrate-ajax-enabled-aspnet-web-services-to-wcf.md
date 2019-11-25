---
title: Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 60e3088b9075464176c328af1f52676a69c4990f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976133"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
В этом разделе описаны процедуры переноса базовой службы ASP.NET AJAX в эквивалентную службу Windows Communication Foundation (WCF) с поддержкой AJAX. Здесь показано, как создать функционально эквивалентную версию WCF службы ASP.NET AJAX. Затем две службы можно использовать параллельно, или службу WCF можно использовать для замены службы ASP.NET AJAX.

 Перенос существующей службы AJAX ASP.NET в службу WCF AJAX предоставляет следующие преимущества:

- службу AJAX можно сделать доступной в качестве службы SOAP при минимальной дополнительной настройке;

- Вы можете воспользоваться преимуществами таких функций WCF, как трассировка и т. д.

 В следующих процедурах предполагается, что вы используете Visual Studio 2012.

 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в примере после процедур.

 Дополнительные сведения о предоставлении службы WCF через конечную точку с поддержкой AJAX см. в разделе [Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) .

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Создание и тестирование приложения веб-службы ASP.NET

1. Откройте Visual Studio 2012.

2. В меню **файл** выберите **создать**, затем **проект**, **веб**, а затем выберите **ASP.NET веб-служба приложение**.

3. Присвойте проекту имя `ASPHello` и нажмите кнопку **ОК**.

4. В файле Service1.asmx.cs снимите знаки комментария со строки, содержащей `System.Web.Script.Services.ScriptService]`, чтобы включить для этой службы поддержку AJAX.

5. В меню **Сборка** выберите пункт **построить решение**.

6. В меню **Отладка** выберите пункт **Запуск без отладки**.

7. На созданной веб-странице выберите операцию `HelloWorld`.

8. Нажмите кнопку **Invoke (вызвать** ) на странице теста `HelloWorld`. Должен появиться следующий XML-ответ.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Этот ответ подтверждает, что имеется функционирующая служба AJAX ASP.NET, и что эта служба доступна через конечную точку Service1.asmx/HelloWorld, которая отвечает на запросы HTTP POST и возвращает XML-код.

     Теперь все готово для преобразования этой службы для использования службы WCF AJAX.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Создание эквивалентного приложения службы AJAX WCF

1. Щелкните правой кнопкой мыши проект **асфелло** и выберите **Добавить**, затем **новый элемент**и **Служба WCF с поддержкой AJAX**.

2. Присвойте службе имя `WCFHello` и нажмите кнопку **Добавить**.

3. Откройте файл WCFHello.svc.cs.

4. В Service1.asmx.cs скопируйте следующую реализацию операции `HelloWorld`.

    ```csharp
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

5. Вставьте скопированную реализацию `HelloWorld` операции в файл WCFHello.svc.cs вместо следующего кода.

    ```csharp
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6. Укажите `Namespace` атрибут <xref:System.ServiceModel.ServiceContractAttribute> как `WCFHello`.

    ```csharp
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7. Добавьте <xref:System.ServiceModel.Web.WebInvokeAttribute> в `HelloWorld` операцию и присвойте свойству <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> значение, возвращающее <xref:System.ServiceModel.Web.WebMessageFormat.Xml>. Обратите внимание, что если это свойство не задано, будет возвращаться тип <xref:System.ServiceModel.Web.WebMessageFormat.Json>.

    ```csharp
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8. В меню **Сборка** выберите пункт **построить решение**.

9. Откройте файл Вкфхелло. svc и в меню **Отладка** выберите **Запуск без отладки**.

10. Теперь служба предоставляет конечную точку на `WCFHello.svc/HelloWorld`, которая реагирует на HTTP-запросы POST. Запросы HTTP POST невозможно тестировать с помощью браузера, но конечная точка возвращает следующий XML-код.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. `WCFHello.svc/HelloWorld` и конечные точки `Service1.aspx/HelloWorld` теперь функционально эквивалентны.

## <a name="example"></a>Пример
 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в следующем примере.

```csharp
//This is the ASP.NET code in the Service1.asmx.cs file.

using System;
using System.Collections;
using System.ComponentModel;
using System.Data;
using System.Linq;
using System.Web;
using System.Web.Services;
using System.Web.Services.Protocols;
using System.Xml.Linq;
using System.Web.Script.Services;

namespace ASPHello
{
    /// <summary>
    /// Summary description for Service1.
    /// </summary>
    [WebService(Namespace = "http://tempuri.org/")]
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]
    [ToolboxItem(false)]
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.
    [System.Web.Script.Services.ScriptService]
    public class Service1 : System.Web.Services.WebService
    {

        [WebMethod]
        public string HelloWorld()
        {
            return "Hello World";
        }
    }
}

//This is the WCF code in the WCFHello.svc.cs file.
using System;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.ServiceModel.Web;

namespace ASPHello
{
    [ServiceContract(Namespace = "WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class WCFHello
    {
        // Add [WebInvoke] attribute to use HTTP GET.
        [OperationContract]
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
        public string HelloWorld()
        {
            return "Hello World";
        }

        // Add more operations here and mark them with [OperationContract].
    }
}
```

 Тип <xref:System.Xml.XmlDocument> не поддерживается классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, потому что его невозможно сериализовать с помощью класса <xref:System.Xml.Serialization.XmlSerializer>. Можно использовать тип <xref:System.Xml.Linq.XDocument> или сериализовать свойство <xref:System.Xml.XmlDocument.DocumentElement%2A>.

 Если веб-службы ASMX обновляются и мигрируют параллельно службам WCF, Избегайте сопоставления двух типов с одним и тем же именем на клиенте. Это приведет к исключению при сериализации, если в атрибутах <xref:System.Web.Services.WebMethodAttribute> и <xref:System.ServiceModel.ServiceContractAttribute> будет использоваться один и тот же тип:

- Если сначала добавляется служба WCF, вызов метода в веб-службе ASMX приводит к возникновению исключения в <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29>, так как определение стиля WCF для порядка в прокси-сервере имеет приоритет.

- Если сначала добавляется веб-служба ASMX, вызов метода в службе WCF вызывает исключение в <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, так как определение стиля веб-службы для порядка в прокси-сервере имеет приоритет.

 Имеются важные различия в работе класса <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и класса <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET. Например, класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> представляет словарь в виде массива пар "ключ-значение", а класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET представляет словарь в виде фактических объектов JSON. Ниже представлен словарь в формате AJAX ASP.NET.

```csharp
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Этот словарь состоит из объектов JSON, как показано в следующем списке:

- [{"Key":"one","Value":1},{"Key":"two","Value":2}] - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

- {"One": 1, "два": 2} ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 Класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> обладает более широкими возможностями в том смысле, что он может обрабатываться словари, где тип ключа не является строковым; класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> не поддерживает такой возможности. Однако последний класс лучше работает с форматом JSON.

 Ключевые различия между этими сериализаторами показаны в следующей таблице.

|Категория различий|DataContractJsonSerializer|JavaScriptSerializer AJAX ASP.NET|
|-----------------------------|--------------------------------|---------------------------------------|
|Десериализация пустого буфера (new byte[0]) в <xref:System.Object> (или <xref:System.Uri>, или некоторые другие классы).|SerializationException|null|
|Сериализация <xref:System.DBNull.Value>|{} (или {"__type": "#System"})|Null|
|Сериализация закрытых членов типов [Serializable]|Сериализуются|Не сериализуются|
|Сериализация открытых свойств типов <xref:System.Runtime.Serialization.ISerializable>|Не сериализуются|Сериализуются|
|Расширения JSON|Удовлетворяет спецификации JSON, которая требует заключать имена членов объектов в кавычки ({"a":"hello"}).|Поддерживает имена членов объектов без кавычек ({a:"hello"}).|
|Время в формате UTC (<xref:System.DateTime>)|Не поддерживает формат "\\/дате (123456789U)\\/" или "\\/дате\\(\d + (U&#124;(\\+\\-[\d{4}]))?\\)\\\\/) ".|Поддерживает формат "\\/дате (123456789U)\\/" and "\\/дате\\(\d + (U&#124;(\\+\\-[\d{4}]))?\\)\\\\/) "как значения DateTime.|
|Представление словарей|Массив KeyValuePair\<K, V >, обрабатывает типы ключей, которые не являются строками.|Фактические объекты JSON, но обрабатывает только ключи строковых типов|
|Escape-символы|Всегда с escape-символом прямой косой черты (/); нельзя использовать недопустимые символы JSON без escape-символа, например "\n"|Значения DateTime с escape-символом прямой косой черты (/)|

## <a name="see-also"></a>См. также

- [Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
