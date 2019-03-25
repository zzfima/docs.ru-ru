---
title: Практическое руководство. Миграция с поддержкой AJAX веб-служб ASP.NET в WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 3c7052a67e756ae0c3fa1692c3ed746419384de4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410944"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Практическое руководство. Миграция с поддержкой AJAX веб-служб ASP.NET в WCF
В этом разделе описаны процедуры по переносу базовой службы ASP.NET AJAX для службы с поддержкой AJAX Windows Communication Foundation (WCF). В этом примере показано создание функционально эквивалентны WCF версию службы ASP.NET AJAX. Две службы затем используется рядом друг с другом или службы WCF можно использовать для замены службы ASP.NET AJAX.

 Перенос существующего ASP.NET AJAX вызовы между службами WCF AJAX предоставляет следующие преимущества:

-   службу AJAX можно сделать доступной в качестве службы SOAP при минимальной дополнительной настройке;

-   Воспользуйтесь преимуществами функций WCF, таких как трассировка и т.д.

 В следующих процедурах предполагается, что вы используете Visual Studio 2012.

 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в примере после процедур.

 Дополнительные сведения о предоставлении доступа к службе WCF через конечную точку с поддержкой AJAX, см. в разделе [как: Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) раздела.

### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Создание и тестирование приложения веб-службы ASP.NET

1.  Откройте Visual Studio 2012.

2.  Из **файл** меню, выберите **New**, затем **проекта**, затем **Web**, а затем выберите **приложения веб-службы ASP.NET** .

3.  Назовите проект `ASPHello` и нажмите кнопку **ОК**.

4.  В файле Service1.asmx.cs снимите знаки комментария со строки, содержащей `System.Web.Script.Services.ScriptService]`, чтобы включить для этой службы поддержку AJAX.

5.  Из **построения** меню, выберите **построить решение**.

6.  В меню **Отладка** выберите пункт **Запуск без отладки**.

7.  На созданной веб-странице выберите операцию `HelloWorld`.

8.  Нажмите кнопку **Invoke** кнопку `HelloWorld` тестовую страницу. Должен появиться следующий XML-ответ.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <string xmlns="http://tempuri.org/">Hello World</string>
    ```

9. Этот ответ подтверждает, что имеется функционирующая служба AJAX ASP.NET, и что эта служба доступна через конечную точку Service1.asmx/HelloWorld, которая отвечает на запросы HTTP POST и возвращает XML-код.

     Теперь все готово для преобразования этой службы для использования службы WCF AJAX.

### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Создание эквивалентного приложения службы AJAX WCF

1.  Щелкните правой кнопкой мыши **ASPHello** проекта и выберите **добавить**, затем **новый элемент**, а затем **служба WCF с поддержкой AJAX**.

2.  Назовите службу `WCFHello` и нажмите кнопку **добавить**.

3.  Откройте файл WCFHello.svc.cs.

4.  Из файла Service1.asmx.cs скопируйте следующую реализацию `HelloWorld` операции.

    ```
    public string HelloWorld()
    {
         return "Hello World";
    }
    ```

5.  Вставьте скопированную реализацию `HelloWorld` операции в файл WCFHello.svc.cs вместо следующего кода.

    ```
    public void DoWork()
    {
          // Add your operation implementation here
          return;
    }
    ```

6.  Укажите `Namespace` для атрибута <xref:System.ServiceModel.ServiceContractAttribute> как `WCFHello`.

    ```
    [ServiceContract(Namespace="WCFHello")]
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]
    public class WCFHello
    { … }
    ```

7.  Добавить <xref:System.ServiceModel.Web.WebInvokeAttribute> для `HelloWorld` операции и набор <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> возвращаемое свойство <xref:System.ServiceModel.Web.WebMessageFormat.Xml>. Обратите внимание, что если это свойство не задано, будет возвращаться тип <xref:System.ServiceModel.Web.WebMessageFormat.Json>.

    ```
    [OperationContract]
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]
    public string HelloWorld()
    {
        return "Hello World";
    }
    ```

8.  Из **построения** меню, выберите **построить решение**.

9. Откройте файл WCFHello.svc и из **Отладка** меню, выберите **Запуск без отладки**.

10. Теперь служба предоставляет конечную точку по `WCFHello.svc/HelloWorld`, которая отвечает на запросы HTTP POST. Запросы HTTP POST невозможно тестировать с помощью браузера, но конечная точка возвращает следующий XML-код.

    ```xml
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>
    ```

11. `WCFHello.svc/HelloWorld` И `Service1.aspx/HelloWorld` конечные точки теперь функционально эквивалентны.

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

 Если веб-службы ASMX обновляются и перенести side-by-side служб WCF, избегайте сопоставления двух типов с тем же именем на стороне клиента. Это приведет к исключению при сериализации, если в атрибутах <xref:System.Web.Services.WebMethodAttribute> и <xref:System.ServiceModel.ServiceContractAttribute> будет использоваться один и тот же тип:

-   Если сначала добавляется служба WCF, вызывает метод на веб-службе ASMX приводит к исключению в <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> так, как приоритет WCF стиль определения порядка в прокси-сервер.

-   Если сначала добавляется веб-службы ASMX, вызов метода в службе WCF приводит к исключению в <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> так, как приоритет веб-службы стиль определения порядка в прокси-сервер.

 Имеются важные различия в работе класса <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и класса <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET. Например, класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> представляет словарь в виде массива пар "ключ-значение", а класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> AJAX ASP.NET представляет словарь в виде фактических объектов JSON. Ниже представлен словарь в формате AJAX ASP.NET.

```
Dictionary<string, int> d = new Dictionary<string, int>();
d.Add("one", 1);
d.Add("two", 2);
```

 Этот словарь состоит из объектов JSON, как показано в следующем списке:

-   [{"Key":"one","Value":1},{"Key":"two","Value":2}] - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

-   {«one»: 1, «two»: 2} с ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>

 Класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> обладает более широкими возможностями в том смысле, что он может обрабатываться словари, где тип ключа не является строковым; класс <xref:System.Web.Script.Serialization.JavaScriptSerializer> не поддерживает такой возможности. Однако последний класс лучше работает с форматом JSON.

 Ключевые различия между этими сериализаторами показаны в следующей таблице.

|Категория различий|DataContractJsonSerializer|JavaScriptSerializer AJAX ASP.NET|
|-----------------------------|--------------------------------|---------------------------------------|
|Десериализация пустого буфера (new byte[0]) в <xref:System.Object> (или <xref:System.Uri>, или некоторые другие классы).|SerializationException|null|
|Сериализация <xref:System.DBNull.Value>|{} (или {«__type»: «#System»})|Null|
|Сериализация закрытых членов типов [Serializable]|Сериализуются|Не сериализуются|
|Сериализация открытых свойств типов <xref:System.Runtime.Serialization.ISerializable>|Не сериализуются|Сериализуются|
|Расширения JSON|Удовлетворяет спецификации JSON, которая требует заключать имена членов объектов в кавычки ({"a":"hello"}).|Поддерживает имена членов объектов без кавычек ({a:"hello"}).|
|Время в формате UTC (<xref:System.DateTime>)|Не поддерживает формат "\\/Date(123456789U)\\/» или"\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".|Поддерживает формат "\\/Date(123456789U)\\/» и"\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/)» как значения даты и времени.|
|Представление словарей|Массив KeyValuePair\<K, V >, обрабатывает типы ключей, которые не являются строками.|Фактические объекты JSON, но обрабатывает только ключи строковых типов|
|Escape-символы|Всегда с escape-символом прямой косой черты (/); нельзя использовать недопустимые символы JSON без escape-символа, например "\n"|Значения DateTime с escape-символом прямой косой черты (/)|

## <a name="see-also"></a>См. также
- [Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
