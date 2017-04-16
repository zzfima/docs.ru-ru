---
title: "Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF
В этом разделе описаны процедуры по переносу базовой службы AJAX ASP.NET в эквивалентную службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с поддержкой AJAX.  В нем показано, как создать функционально эквивалентную [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-версию службы AJAX ASP.NET.  Две службы можно использовать параллельно, либо можно заменить службу AJAX ASP.NET службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Перенос имеющейся службы AJAX ASP.NET в службу AJAX [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет получить следующие преимущества:  
  
-   службу AJAX можно сделать доступной в качестве службы SOAP при минимальной дополнительной настройке;  
  
-   можно использовать такие возможности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], как трассировка и т. д.  
  
 В следующих процедурах предполагается, что используется [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
 Код, получаемый в результате применения описанных в этом разделе процедур, приведен в примере после процедур.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] представлении службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] посредством конечной точки с поддержкой технологии AJAX см. в разделе [Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### Создание и тестирование приложения веб\-службы ASP.NET  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В меню **Файл** выберите **Создать** и щелкните пункт **Проект**, выберите **Веб**, затем выберите **Приложение веб\-служб ASP.NET**.  
  
3.  Задайте имя проекта `ASPHello` и нажмите кнопку **ОК**.  
  
4.  В файле Service1.asmx.cs снимите знаки комментария со строки, содержащей `System.Web.Script.Services.ScriptService]`, чтобы включить для этой службы поддержку AJAX.  
  
5.  В меню **Построить** выберите пункт **Построить решение**.  
  
6.  В меню **Отладка** выберите пункт **Запуск без отладки**.  
  
7.  На созданной веб\-странице выберите операцию `HelloWorld`.  
  
8.  На тестовой странице `HelloWorld` нажмите кнопу **Вызвать**.  Должен появиться следующий XML\-ответ.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. Этот ответ подтверждает, что имеется функционирующая служба AJAX ASP.NET, и что эта служба доступна через конечную точку Service1.asmx\/HelloWorld, которая отвечает на запросы HTTP POST и возвращает XML\-код.  
  
     Теперь эту службу можно преобразовать в службу AJAX [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### Создание эквивалентного приложения службы AJAX WCF  
  
1.  Щелкните правой кнопкой мыши проект **ASPHello** и выберите команды **Добавить** и **Добавить новый элемент**, после чего выберите вариант **Служба WCF с поддержкой AJAX**.  
  
2.  Назовите службу `WCFHello` и нажмите кнопку **Добавить**.  
  
3.  Откройте файл WCFHello.svc.cs.  
  
4.  Из файла Service1.asmx.cs скопируйте следующую реализацию операции `HelloWorld`.  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  Вставьте скопированную реализацию операции `HelloWorld` в файл WCFHello.svc.cs вместо следующего кода.  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  Задайте для атрибута `Namespace` объекта <xref:System.ServiceModel.ServiceContractAttribute> значение `WCFHello`.  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  Добавьте объект <xref:System.ServiceModel.Web.WebInvokeAttribute> в операцию `HelloWorld` и задайте свойство <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>, возвращающее значение <xref:System.ServiceModel.Web.WebMessageFormat>.  Обратите внимание, что если это свойство не задано, будет возвращаться тип <xref:System.ServiceModel.Web.WebMessageFormat>.  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  В меню **Построить** выберите пункт **Построить решение**.  
  
9. Откройте файл WCFHello.svc и в меню **Отладка** выберите команду **Запуск без отладки**.  
  
10. Теперь служба предоставляет конечную точку с адресом `WCFHello.svc/HelloWorld`, которая отвечает на запросы HTTP POST.  Запросы HTTP POST невозможно тестировать с помощью браузера, но конечная точка возвращает следующий XML\-код.  
  
    ```  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. Теперь конечные точки `WCFHello.svc/HelloWorld` и `Service1.aspx/HelloWorld` функционально эквивалентны.  
  
## Пример  
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
  
 Тип <xref:System.Xml.XmlDocument> не поддерживается классом <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, потому что его невозможно сериализовать с помощью класса <xref:System.Xml.Serialization.XmlSerializer>.  Можно использовать тип <xref:System.Xml.Linq.XDocument> или сериализовать свойство <xref:System.Xml.XmlDocument.DocumentElement%2A>.  
  
 Если веб\-службы ASMX обновляются и параллельно переносятся на платформу служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], следует избегать сопоставления двух типов одному имени клиента.  Это приведет к исключению при сериализации, если в атрибутах <xref:System.Web.Services.WebMethodAttribute> и <xref:System.ServiceModel.ServiceContractAttribute> будет использоваться один и тот же тип:  
  
-   если сначала добавляется служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], вызов метода в веб\-службе ASMX приводит к исключению в методе <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29>, поскольку имеет приоритет стиль определения порядка в прокси [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)];  
  
-   если сначала добавляется веб\-служба ASMX, вызов метода в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] приводит к исключению в объекте <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, поскольку имеет приоритет стиль определения порядка в прокси веб\-службы.  
  
 Имеются важные различия в работе класса <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и класса <xref:System.Web.Script.Serialization.JavascriptSerializer> AJAX ASP.NET.  Например, класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> представляет словарь в виде массива пар "ключ\-значение", а класс <xref:System.Web.Script.Serialization.JavascriptSerializer> AJAX ASP.NET представляет словарь в виде фактических объектов JSON.  Ниже представлен словарь в формате AJAX ASP.NET.  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add(“one”, 1);  
d.Add(“two”, 2);  
```  
  
 Этот словарь состоит из объектов JSON, как показано в следующем списке:  
  
-   \[{"Key":"one","Value":1},{"Key":"two","Value":2}\] \- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>  
  
-   {“one”:1,”two”:2} \- <xref:System.Web.Script.Serialization.JavascriptSerializer> AJAX ASP.NET  
  
 Класс <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> обладает более широкими возможностями в том смысле, что он может обрабатываться словари, где тип ключа не является строковым; класс <xref:System.Web.Script.Serialization.JavascriptSerializer> не поддерживает такой возможности.  Однако последний класс лучше работает с форматом JSON.  
  
 Ключевые различия между этими сериализаторами показаны в следующей таблице.  
  
|Категория различий|DataContractJsonSerializer|JavaScriptSerializer AJAX ASP.NET|  
|------------------------|--------------------------------|---------------------------------------|  
|Десериализация пустого буфера \(new byte\[0\]\) в <xref:System.Object> \(или <xref:System.Uri>, или некоторые другие классы\).|SerializationException|null|  
|Сериализация <xref:System.DBNull.Value>|{} \(или {"\_\_type":"\#System"}\)|Null|  
|Сериализация закрытых членов типов \[Serializable\]|Сериализуются|Не сериализуются|  
|Сериализация открытых свойств типов <xref:System.Runtime.Serialization.ISerializable>|Не сериализуются|Сериализуются|  
|Расширения JSON|Удовлетворяет спецификации JSON, которая требует заключать имена членов объектов в кавычки \({"a":"hello"}\).|Поддерживает имена членов объектов без кавычек \({a:"hello"}\).|  
|Время в формате UTC \(<xref:System.DateTime>\)|Не поддерживает форматы «\\\/Date\(123456789U\)\\\/» и «\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)".|Поддерживает формат «\\\/Date\(123456789U\)\\\/» и «\\\/Date\\\(\\d\+\(U&#124;\(\\\+\\\-\[\\d{4}\]\)\)?  \\\)\\\\\/\)» в качестве значений DateTime.|  
|Представление словарей|Массив пар «ключ\-значение»\<K,V\>, обрабатывает ключи нестроковых типов|Фактические объекты JSON, но обрабатывает только ключи строковых типов|  
|Escape\-символы|Всегда с escape\-символом прямой косой черты \(\/\); нельзя использовать недопустимые символы JSON без escape\-символа, например "\\n"|Значения DateTime с escape\-символом прямой косой черты \(\/\)|  
  
## См. также  
 [Как использовать конфигурацию для добавления конечной точки ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)