---
title: "Как создать службу, принимающую произвольные данные с использованием модели программирования WCF REST"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e566c15a-b600-4e4a-be3a-4af43e767dae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 170149f5a6c495b3f22b9fd30f79ecdda87789b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a>Как создать службу, принимающую произвольные данные с использованием модели программирования WCF REST
Иногда разработчики должны полностью управлять тем, как данные возвращаются из операции службы. Это требуется, когда операция службы должна возвращать данные в формате, не поддерживаемом системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В данном разделе рассматривается использование модели веб-программирования REST [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для создания службы, получающей произвольные данные.  
  
### <a name="to-implement-the-service-contract"></a>Реализация контракта службы  
  
1.  Определите контракт службы. Операция, получающая произвольные данные, должна иметь параметр <xref:System.IO.Stream>. Это должен быть единственный параметр, передаваемый в теле запроса. Описанная в этом примере операция также принимает параметр filename. Этот параметр передается в URL-адресе запроса. Чтобы указать, что параметр передается в URL-адресе, можно задать шаблон <xref:System.UriTemplate> в атрибуте <xref:System.ServiceModel.Web.WebInvokeAttribute>. В этом случае URI, который используется для вызова этого метода, оканчивается на «UploadFile/Some-Filename». Часть URI-шаблон «{filename}» указывает, что параметр операции filename передается в URI, используемый для вызова операции.  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  Реализуйте контракт службы. У контракта имеется только один метод `UploadFile`, который получает файл из произвольных данных в потоке. Операция считывает поток, подсчитывая количество считанных байтов, а затем отображает имя файла и количество считанных байтов.  
  
    ```csharp  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
    ```  
  
### <a name="to-host-the-service"></a>Размещение службы  
  
1.  Создайте консольное приложение для размещения службы.  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2.  Создайте переменную для хранения базового адреса службы в методе `Main`.  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  Создайте экземпляр <xref:System.ServiceModel.ServiceHost> для службы, задающий класс службы и базовый адрес.  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  Добавьте конечную точку, задающую контракт, <xref:System.ServiceModel.WebHttpBinding> и <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  Откройте узел службы. Служба готова к получению запросов.  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a>Вызов службы программным образом  
  
1.  Создайте запрос <xref:System.Net.HttpWebRequest> с кодом URI, используемым для вызова службы. В этом коде базовый адрес объединяется со строкой `"/UploadFile/Text"`. Фрагмент `"UploadFile"` кода URI задает вызываемую операцию. Фрагмент `"Test.txt"` кода URI задает параметр filename для передачи в операцию `UploadFile`. Оба эти элемента сопоставляются с шаблоном <xref:System.UriTemplate>, применяемым к контракту операции.  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2.  Для свойства <xref:System.Net.HttpWebRequest.Method%2A> объекта <xref:System.Net.HttpWebRequest> установите значение `POST`, а для свойства <xref:System.Net.HttpWebRequest.ContentType%2A> - значение `"text/plain"`. Эти значения указывают службе на то, что код отправляет данные, и эти данные имеют формат обычного текста.  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  Вызовите метод <xref:System.Net.HttpWebRequest.GetRequestStream%2A>, чтобы получить поток запроса, создайте отправляемые данные, запишите данные в поток запроса и закройте поток.  
  
    ```csharp  
    Stream reqStream = req.GetRequestStream();  
    byte[] fileToSend = new byte[12345];  
    for (int i = 0; i < fileToSend.Length; i++)  
       {  
           fileToSend[i] = (byte)('a' + (i % 26));  
       }  
    reqStream.Write(fileToSend, 0, fileToSend.Length);  
    reqStream.Close();  
    ```  
  
4.  Получите ответ от службы, вызвав метод <xref:System.Net.HttpWebRequest.GetResponse%2A>, и выведите данные ответа на консоль.  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5.  Закройте узел службы.  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен полный код этого примера.  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Net;  
  
namespace ReceiveRawData  
{  
    [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    public class RawDataService : IReceiveData  
    {  
        public void UploadFile(string fileName, Stream fileContents)  
        {  
            byte[] buffer = new byte[10000];  
            int bytesRead, totalBytesRead = 0;  
            do  
            {  
                bytesRead = fileContents.Read(buffer, 0, buffer.Length);  
                totalBytesRead += bytesRead;  
            } while (bytesRead > 0);  
            Console.WriteLine("Service: Received file {0} with {1} bytes", fileName, totalBytesRead);  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Host opened");  
  
            HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
            req.Method = "POST";  
            req.ContentType = "text/plain";  
            Stream reqStream = req.GetRequestStream();  
            byte[] fileToSend = new byte[12345];  
            for (int i = 0; i < fileToSend.Length; i++)  
            {  
                fileToSend[i] = (byte)('a' + (i % 26));  
            }  
            reqStream.Write(fileToSend, 0, fileToSend.Length);  
            reqStream.Close();  
            HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
            Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   При компиляции этого кода задайте ссылки на файлы System.ServiceModel.dll и System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>См. также  
 [UriTemplate и UriTemplateTable](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Общие сведения о модели веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
