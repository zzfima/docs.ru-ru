---
title: "Как создать службу, возвращающую произвольные данные, с использованием модели программирования WCF Web HTTP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0283955a-b4ae-458d-ad9e-6fbb6f529e3d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e1d808d4daf91b5ff89b05cab8359c90090f293
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-that-returns-arbitrary-data-using-the-wcf-web-http-programming-model"></a><span data-ttu-id="5ecc5-102">Как создать службу, возвращающую произвольные данные, с использованием модели программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="5ecc5-102">How to: Create a Service That Returns Arbitrary Data Using The WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="5ecc5-103">Иногда разработчики должны полностью управлять тем, как данные возвращаются из операции службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-103">Sometimes developers must have full control of how data is returned from a service operation.</span></span> <span data-ttu-id="5ecc5-104">Это случается, когда операция службы должна возвращать данные в формате, не поддерживаемом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ecc5-104">This is the case when a service operation must return data in a format not supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="5ecc5-105">В этом разделе рассматривается использование модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP для создания такой службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-105">This topic discusses using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WEB HTTP Programming Model to create such a service.</span></span> <span data-ttu-id="5ecc5-106">В этой службе имеется одна операция, которая возвращает поток.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-106">This service has one operation that returns a stream.</span></span>  
  
### <a name="to-implement-the-service-contract"></a><span data-ttu-id="5ecc5-107">Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="5ecc5-107">To implement the service contract</span></span>  
  
1.  <span data-ttu-id="5ecc5-108">Определите контракт службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-108">Define the service contract.</span></span> <span data-ttu-id="5ecc5-109">Контракт называется `IImageServer` и в нем имеется один метод под названием `GetImage`, который возвращает поток <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-109">The contract is called `IImageServer` and has one method called `GetImage` that returns a <xref:System.IO.Stream>.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IImageServer  
        {  
            [WebGet]  
            Stream GetImage(int width, int height);  
        }  
    ```  
  
     <span data-ttu-id="5ecc5-110">Поскольку этот метод возвращает поток <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предполагает, что операция полностью управляет байтами, возвращаемыми из операции службы, и никак не форматирует возвращаемые данные.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-110">Because the method returns a <xref:System.IO.Stream>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assumes that the operation has complete control over the bytes that are returned from the service operation and it applies no formatting to the data that is returned.</span></span>  
  
2.  <span data-ttu-id="5ecc5-111">Реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-111">Implement the service contract.</span></span> <span data-ttu-id="5ecc5-112">В контракте есть только одна операция (`GetImage`).</span><span class="sxs-lookup"><span data-stu-id="5ecc5-112">The contract has only one operation (`GetImage`).</span></span> <span data-ttu-id="5ecc5-113">Этот метод создает растровое изображение и сохраняет его в потоке <xref:System.IO.MemoryStream> в формате JPG.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-113">This method generates a bitmap and then save it to a <xref:System.IO.MemoryStream> in .jpg format.</span></span> <span data-ttu-id="5ecc5-114">Операция затем возвращает этот поток вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-114">The operation then returns that stream to the caller.</span></span>  
  
    ```  
    public class Service : IImageServer  
       {  
           public Stream GetImage(int width, int height)  
           {  
               Bitmap bitmap = new Bitmap(width, height);  
               for (int i = 0; i < bitmap.Width; i++)  
               {  
                   for (int j = 0; j < bitmap.Height; j++)  
                   {  
                       bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                   }  
               }  
               MemoryStream ms = new MemoryStream();  
               bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
               ms.Position = 0;  
               WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
               return ms;  
           }  
       }  
    ```  
  
     <span data-ttu-id="5ecc5-115">Взгляните на последнюю строку кода: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span><span class="sxs-lookup"><span data-stu-id="5ecc5-115">Notice the second to last line of code: `WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";`</span></span>  
  
     <span data-ttu-id="5ecc5-116">Это задает заголовок content-type `"image/jpeg"`.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-116">This sets the content type header to `"image/jpeg"`.</span></span> <span data-ttu-id="5ecc5-117">Хотя в этом образце показано, как вернуть JPG-файл, данный образец можно изменить для возврата любого типа необходимых данных в любом формате.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-117">Although this sample shows how to return a .jpg file, it can be modified to return any type of data that is required, in any format.</span></span> <span data-ttu-id="5ecc5-118">Операция должна получить или создать данные и затем записать их в поток.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-118">The operation must retrieve or generate the data and then write it to a stream.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="5ecc5-119">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="5ecc5-119">To host the service</span></span>  
  
1.  <span data-ttu-id="5ecc5-120">Создайте консольное приложение для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-120">Create a console application to host the service.</span></span>  
  
    ```  
    class Program  
    {  
        static void Main(string[] args)  
        {  
        }   
    }  
    ```  
  
2.  <span data-ttu-id="5ecc5-121">Создайте переменную для хранения базового адреса службы в методе `Main`.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-121">Create a variable to hold the base address for the service within the `Main` method.</span></span>  
  
    ```  
    string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
    ```  
  
3.  <span data-ttu-id="5ecc5-122">Создайте экземпляр <xref:System.ServiceModel.ServiceHost> для службы, задав класс службы и базовый адрес.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-122">Create a <xref:System.ServiceModel.ServiceHost> instance for the service specifying the service class and the base address.</span></span>  
  
    ```  
    ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
    ```  
  
4.  <span data-ttu-id="5ecc5-123">Добавьте конечную точку, используя <xref:System.ServiceModel.WebHttpBinding> и <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-123">Add an endpoint using the <xref:System.ServiceModel.WebHttpBinding> and the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
    ```  
    host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
    ```  
  
5.  <span data-ttu-id="5ecc5-124">Откройте узел службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-124">Open the service host.</span></span>  
  
    ```  
    host.Open()  
    ```  
  
6.  <span data-ttu-id="5ecc5-125">Подождите, пока пользователь нажмет клавишу ВВОД, чтобы завершить работу службы.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-125">Wait until the user presses ENTER to terminate the service.</span></span>  
  
    ```  
    Console.WriteLine("Service is running");  
    Console.Write("Press ENTER to close the host");  
    Console.ReadLine();  
    host.Close();  
    ```  
  
### <a name="to-call-the-raw-service-using-internet-explorer"></a><span data-ttu-id="5ecc5-126">Вызов необработанной службы с помощью Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="5ecc5-126">To call the raw service using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="5ecc5-127">Запустите службу. От службы должно появиться следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="5ecc5-127">Run the service, you should see the following output from the service.</span></span> `Service is running Press ENTER to close the host`  
  
2.  <span data-ttu-id="5ecc5-128">Откройте Internet Explorer и введите `http://localhost:8000/Service/GetImage?width=50&height=40`. Должен появиться желтый прямоугольник с синей диагональной линией, проходящей через центр.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-128">Open Internet Explorer and type in `http://localhost:8000/Service/GetImage?width=50&height=40` you should see a yellow rectangle with a blue diagonal line through the center.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ecc5-129">Пример</span><span class="sxs-lookup"><span data-stu-id="5ecc5-129">Example</span></span>  
 <span data-ttu-id="5ecc5-130">Ниже приведен полный листинг кода для данного раздела.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-130">The following is a complete listing of the code for this topic.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.ServiceModel;  
using System.ServiceModel.Web;  
using System.ServiceModel.Description;  
using System.IO;  
using System.Drawing;  
  
namespace RawImageService  
{  
    // Define the service contract  
    [ServiceContract]  
    public interface IImageServer  
    {  
        [WebGet]  
        Stream GetImage(int width, int height);  
    }  
  
    // implement the service contract  
    public class Service : IImageServer  
    {  
        public Stream GetImage(int width, int height)  
        {  
            // Although this method returns a jpeg, it can be  
            // modified to return any data you want within the stream  
            Bitmap bitmap = new Bitmap(width, height);  
            for (int i = 0; i < bitmap.Width; i++)  
            {  
                for (int j = 0; j < bitmap.Height; j++)  
                {  
                    bitmap.SetPixel(i, j, (Math.Abs(i - j) < 2) ? Color.Blue : Color.Yellow);  
                }  
            }  
            MemoryStream ms = new MemoryStream();  
            bitmap.Save(ms, System.Drawing.Imaging.ImageFormat.Jpeg);  
            ms.Position = 0;  
            WebOperationContext.Current.OutgoingResponse.ContentType = "image/jpeg";  
            return ms;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            string baseAddress = "http://" + Environment.MachineName + ":8000/Service";  
            ServiceHost host = new ServiceHost(typeof(Service), new Uri(baseAddress));  
            host.AddServiceEndpoint(typeof(IImageServer), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
            host.Open();  
            Console.WriteLine("Service is running");  
            Console.Write("Press ENTER to close the host");  
            Console.ReadLine();  
            host.Close();  
  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5ecc5-131">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5ecc5-131">Compiling the Code</span></span>  
  
-   <span data-ttu-id="5ecc5-132">При компиляции образец кода обращается к файлам System.ServiceModel.dll и System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="5ecc5-132">When compiling the sample code reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecc5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5ecc5-133">See Also</span></span>  
 [<span data-ttu-id="5ecc5-134">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="5ecc5-134">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
