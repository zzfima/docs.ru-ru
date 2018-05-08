---
title: Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 048408adf8678c243a225a233cb1173c9b7f869f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a>Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
В этом разделе описаны процедуры по переносу базовой службы ASP.NET AJAX для службы с поддержкой AJAX Windows Communication Foundation (WCF). В этом примере показано создание функционально эквивалентны версии WCF-служб ASP.NET AJAX. Две службы затем могут использоваться параллельно, или службы WCF можно использовать для замены службы ASP.NET AJAX.  
  
 Миграция существующих AJAX ASP.NET службы для службы WCF AJAX предоставляет следующие преимущества:  
  
-   службу AJAX можно сделать доступной в качестве службы SOAP при минимальной дополнительной настройке;  
  
-   Преимущества функций WCF, такие как трассировка и т. д.  
  
 В следующих процедурах предполагается, что используется [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в примере после процедур.  
  
 Дополнительные сведения о предоставлении доступа к службе WCF через конечную точку с поддержкой AJAX см. в разделе [как: использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) раздела.  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a>Создание и тестирование приложения веб-службы ASP.NET  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Из **файл** последовательно выберите пункты **New**, затем **проекта**, затем **Web**и выберите **приложения веб-службы ASP.NET** .  
  
3.  Назовите проект `ASPHello` и нажмите кнопку **ОК**.  
  
4.  В файле Service1.asmx.cs снимите знаки комментария со строки, содержащей `System.Web.Script.Services.ScriptService]`, чтобы включить для этой службы поддержку AJAX.  
  
5.  Из **построения** последовательно выберите пункты **построить решение**.  
  
6.  Из **отладки** последовательно выберите пункты **Запуск без отладки**.  
  
7.  На созданной веб-странице выберите операцию `HelloWorld`.  
  
8.  Нажмите кнопку **Invoke** кнопку `HelloWorld` тестовую страницу. Должен появиться следующий XML-ответ.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. Этот ответ подтверждает, что имеется функционирующая служба AJAX ASP.NET, и что эта служба доступна через конечную точку Service1.asmx/HelloWorld, которая отвечает на запросы HTTP POST и возвращает XML-код.  
  
     Теперь все готово для преобразования эту службу для использования службы WCF AJAX.  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a>Создание эквивалентного приложения службы AJAX WCF  
  
1.  Щелкните правой кнопкой мыши **ASPHello** проект и выберите **добавить**, затем **новый элемент**, а затем **служба WCF с поддержкой AJAX**.  
  
2.  Имя службы `WCFHello` и нажмите кнопку **добавить**.  
  
3.  Откройте файл WCFHello.svc.cs.  
  
4.  Из файла Service1.asmx.cs скопируйте следующую реализацию из `HelloWorld` операции.  
  
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
  
8.  Из **построения** последовательно выберите пункты **построить решение**.  
  
9. Откройте файл WCFHello.svc и из **отладки** последовательно выберите пункты **Запуск без отладки**.  
  
10. Теперь служба предоставляет конечную точку по `WCFHello.svc/HelloWorld`, которая отвечает на запросы HTTP POST. Запросы HTTP POST невозможно тестировать с помощью браузера, но конечная точка возвращает следующий XML-код.  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. `WCFHello.svc/HelloWorld` И `Service1.aspx/HelloWorld` конечные точки теперь функционально эквивалентны.  
  
## <a name="example"></a>Пример  
 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в следующем примере.  
  
```  
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
  
 Если веб-службы ASMX обновляются и перенесены side-by-side службы WCF, избегайте сопоставление двух типов с тем же именем на стороне клиента. Это приведет к исключению при сериализации, если в атрибутах <xref:System.Web.Services.WebMethodAttribute> и <xref:System.ServiceModel.ServiceContractAttribute> будет использоваться один и тот же тип:  
  
-   Если сначала добавляется служба WCF, вызов метода в веб-службе ASMX приводит к исключению в <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> , так как определение стиля WCF порядка в прокси-сервер имеет более высокий приоритет.  
  
-   Если сначала добавляется веб-службы ASMX, вызов метода в службе WCF приводит к исключению в <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> , так как имеет приоритет стиль определения веб-службы, порядка в прокси-сервер.  
  
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
|Время в формате UTC (<xref:System.DateTime>)|Не поддерживает формат «\\/Date(123456789U)\\/» или «\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".|Поддерживает формат «\\/Date(123456789U)\\/» и «\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/)» как значения даты и времени.|  
|Представление словарей|Массив KeyValuePair\<K, V >, обрабатывает типы ключей, которые не являются строками.|Фактические объекты JSON, но обрабатывает только ключи строковых типов|  
|Escape-символы|Всегда с escape-символом прямой косой черты (/); нельзя использовать недопустимые символы JSON без escape-символа, например "\n"|Значения DateTime с escape-символом прямой косой черты (/)|  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
