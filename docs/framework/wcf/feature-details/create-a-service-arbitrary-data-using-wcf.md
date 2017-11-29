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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9541c46d029aa9f4e27a459ffcb9f32a7718039b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-that-accepts-arbitrary-data-using-the-wcf-rest-programming-model"></a><span data-ttu-id="a1ea2-102">Как создать службу, принимающую произвольные данные с использованием модели программирования WCF REST</span><span class="sxs-lookup"><span data-stu-id="a1ea2-102">How to: Create a Service That Accepts Arbitrary Data using the WCF REST Programming Model</span></span>
<span data-ttu-id="a1ea2-103">Иногда разработчики должны полностью управлять тем, как данные возвращаются из операции службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="a1ea2-104">Это требуется, когда операция службы должна возвращать данные в формате, не поддерживаемом системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1ea2-104">This is the case when a service operation must return data in a format not supported by[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="a1ea2-105">В данном разделе рассматривается использование модели веб-программирования REST [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для создания службы, получающей произвольные данные.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST Programming Model to create a service that receives arbitrary data.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="a1ea2-106">Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="a1ea2-106">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="a1ea2-107">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-107">Define the service contract.</span></span> <span data-ttu-id="a1ea2-108">Операция, получающая произвольные данные, должна иметь параметр <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-108">The operation that receives the arbitrary data must have a parameter of type <xref:System.IO.Stream>.</span></span> <span data-ttu-id="a1ea2-109">Это должен быть единственный параметр, передаваемый в теле запроса.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-109">In addition, this parameter must be the only parameter passed in the body of the request.</span></span> <span data-ttu-id="a1ea2-110">Описанная в этом примере операция также принимает параметр filename.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-110">The operation described in this example also takes a filename parameter.</span></span> <span data-ttu-id="a1ea2-111">Этот параметр передается в URL-адресе запроса.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-111">This parameter is passed within the URL of the request.</span></span> <span data-ttu-id="a1ea2-112">Чтобы указать, что параметр передается в URL-адресе, можно задать шаблон <xref:System.UriTemplate> в атрибуте <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-112">You can specify that a parameter is passed within the URL by specifying a <xref:System.UriTemplate> in the <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="a1ea2-113">В этом случае URI, который используется для вызова этого метода, оканчивается на «UploadFile/Some-Filename».</span><span class="sxs-lookup"><span data-stu-id="a1ea2-113">In this case the URI used to call this method ends in "UploadFile/Some-Filename".</span></span> <span data-ttu-id="a1ea2-114">Часть URI-шаблон «{filename}» указывает, что параметр операции filename передается в URI, используемый для вызова операции.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-114">The "{filename}" portion of the URI template specifies that the filename parameter for the operation is passed within the URI used to call the operation.</span></span>  
  
    ```csharp  
     [ServiceContract]  
    public interface IReceiveData  
    {  
        [WebInvoke(UriTemplate = "UploadFile/{fileName}")]  
        void UploadFile(string fileName, Stream fileContents);  
    }  
    ```  
  
2.  <span data-ttu-id="a1ea2-115">Реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-115">Implement the service contract.</span></span> <span data-ttu-id="a1ea2-116">У контракта имеется только один метод `UploadFile`, который получает файл из произвольных данных в потоке.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-116">The contract has only one method, `UploadFile` that receives a file of arbitrary data in a stream.</span></span> <span data-ttu-id="a1ea2-117">Операция считывает поток, подсчитывая количество считанных байтов, а затем отображает имя файла и количество считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-117">The operation reads the stream counting the number of bytes read and then displays the filename and the number of bytes read.</span></span>  
  
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
  
### <a name="to-host-the-service"></a><span data-ttu-id="a1ea2-118">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="a1ea2-118">To host the service</span></span>  
  
1.  <span data-ttu-id="a1ea2-119">Создайте консольное приложение для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-119">Create a console application to host the service.</span></span>  
  
    ```csharp  
    class Program  
    {  
       static void Main(string[] args)  
       {  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="a1ea2-120">Создайте переменную для хранения базового адреса службы в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-120">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```csharp  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="a1ea2-121">Создайте экземпляр <xref:System.ServiceModel.ServiceHost> для службы, задающий класс службы и базовый адрес.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-121">Create a <xref:System.ServiceModel.ServiceHost> instance for the service that specifies the service class and the base address.</span></span>  
  
    ```csharp  
    ServiceHost host = new ServiceHost(typeof(RawDataService), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="a1ea2-122">Добавьте конечную точку, задающую контракт, <xref:System.ServiceModel.WebHttpBinding> и <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-122">Add an endpoint that specifies the contract, <xref:System.ServiceModel.WebHttpBinding>, and <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```csharp  
    host.AddServiceEndpoint(typeof(IReceiveData), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="a1ea2-123">Откройте узел службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-123">Open the service host.</span></span> <span data-ttu-id="a1ea2-124">Служба готова к получению запросов.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-124">The service is now ready to receive requests.</span></span>  
  
    ```csharp  
    host.Open();  
    Console.WriteLine("Host opened");  
    ```  
  
### <a name="to-call-the-service-programmatically"></a><span data-ttu-id="a1ea2-125">Вызов службы программным образом</span><span class="sxs-lookup"><span data-stu-id="a1ea2-125">To call the service programmatically</span></span>  
  
1.  <span data-ttu-id="a1ea2-126">Создайте запрос <xref:System.Net.HttpWebRequest> с кодом URI, используемым для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-126">Create a <xref:System.Net.HttpWebRequest> with the URI used to call the service.</span></span> <span data-ttu-id="a1ea2-127">В этом коде базовый адрес объединяется со строкой `"/UploadFile/Text"`.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-127">In this code, the base address is combined with `"/UploadFile/Text"`.</span></span> <span data-ttu-id="a1ea2-128">Фрагмент `"UploadFile"` кода URI задает вызываемую операцию.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-128">The `"UploadFile"` portion of the URI specifies the operation to call.</span></span> <span data-ttu-id="a1ea2-129">Фрагмент `"Test.txt"` кода URI задает параметр filename для передачи в операцию `UploadFile`.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-129">The `"Test.txt"` portion of the URI specifies the filename parameter to pass to the `UploadFile` operation.</span></span> <span data-ttu-id="a1ea2-130">Оба эти элемента сопоставляются с шаблоном <xref:System.UriTemplate>, применяемым к контракту операции.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-130">Both of these items map to the <xref:System.UriTemplate> applied to the operation contract.</span></span>  
  
    ```csharp  
    HttpWebRequest req = (HttpWebRequest)HttpWebRequest.Create(baseAddress + "/UploadFile/Test.txt");  
    ```  
  
2.  <span data-ttu-id="a1ea2-131">Для свойства <xref:System.Net.HttpWebRequest.Method%2A> объекта <xref:System.Net.HttpWebRequest> установите значение `POST`, а для свойства <xref:System.Net.HttpWebRequest.ContentType%2A> - значение `"text/plain"`.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-131">Set the <xref:System.Net.HttpWebRequest.Method%2A> property of the <xref:System.Net.HttpWebRequest> to `POST` and the <xref:System.Net.HttpWebRequest.ContentType%2A> property to `"text/plain"`.</span></span> <span data-ttu-id="a1ea2-132">Эти значения указывают службе на то, что код отправляет данные, и эти данные имеют формат обычного текста.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-132">This tells the service that the code is sending data and that data is in plain text.</span></span>  
  
    ```csharp  
    req.Method = "POST";  
    req.ContentType = "text/plain";  
    ```  
  
3.  <span data-ttu-id="a1ea2-133">Вызовите метод <xref:System.Net.HttpWebRequest.GetRequestStream%2A>, чтобы получить поток запроса, создайте отправляемые данные, запишите данные в поток запроса и закройте поток.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-133">Call <xref:System.Net.HttpWebRequest.GetRequestStream%2A> to get the request stream, create the data to send, write that data to the request stream, and close the stream.</span></span>  
  
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
  
4.  <span data-ttu-id="a1ea2-134">Получите ответ от службы, вызвав метод <xref:System.Net.HttpWebRequest.GetResponse%2A>, и выведите данные ответа на консоль.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-134">Get the response from the service by calling <xref:System.Net.HttpWebRequest.GetResponse%2A> and display the response data to the console.</span></span>  
  
    ```csharp  
    HttpWebResponse resp = (HttpWebResponse)req.GetResponse();  
    Console.WriteLine("Client: Receive Response HTTP/{0} {1} {2}", resp.ProtocolVersion, (int)resp.StatusCode, resp.StatusDescription);  
    ```  
  
5.  <span data-ttu-id="a1ea2-135">Закройте узел службы.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-135">Close the service host.</span></span>  
  
    ```csharp  
    host.Close();  
    ```  
  
## <a name="example"></a><span data-ttu-id="a1ea2-136">Пример</span><span class="sxs-lookup"><span data-stu-id="a1ea2-136">Example</span></span>  
 <span data-ttu-id="a1ea2-137">Ниже приведен полный код этого примера.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-137">The following is a complete listing of the code for this example.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1ea2-138">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a1ea2-138">Compiling the Code</span></span>  
  
-   <span data-ttu-id="a1ea2-139">При компиляции этого кода задайте ссылки на файлы System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="a1ea2-139">When compiling the code reference System.ServiceModel.dll and System.ServiceModel.Web.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ea2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a1ea2-140">See Also</span></span>  
 [<span data-ttu-id="a1ea2-141">UriTemplate и UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="a1ea2-141">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 [<span data-ttu-id="a1ea2-142">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="a1ea2-142">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="a1ea2-143">Общие сведения о модели программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="a1ea2-143">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
