---
title: Создание интернет-запросов
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 80e3a6bd199691df9391e88d5a64fab5df2a08a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048618"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="cb055-102">Создание интернет-запросов</span><span class="sxs-lookup"><span data-stu-id="cb055-102">Creating Internet Requests</span></span>
<span data-ttu-id="cb055-103">Приложения создают экземпляры <xref:System.Net.WebRequest> с помощью метода <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb055-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cb055-104">Этот статический метод создает класс, производный от **WebRequest**, на основе переданной ему схемы URI.</span><span class="sxs-lookup"><span data-stu-id="cb055-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="cb055-105">Запросы Web, File и FTP</span><span class="sxs-lookup"><span data-stu-id="cb055-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="cb055-106">На платформе .NET Framework представлен класс <xref:System.Net.HttpWebRequest>, который является производным от **WebRequest** и обеспечивает обработку запросов HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb055-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="cb055-107">В большинстве случаев класс **WebRequest** предоставляет все свойства, необходимые для выполнения запроса. Тем не менее при необходимости вы можете приводить объекты **WebRequest**, созданные методом **WebRequest.Create**, к типу **HttpWebRequest** для доступа к свойствам запроса, относящимся к протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="cb055-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="cb055-108">Аналогичным образом, объект **HttpWebResponse** обрабатывает ответы на запросы HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb055-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="cb055-109">Для доступа к свойствам объекта **HttpWebResponse**, относящимся к протоколу HTTP, необходимо привести объекты **WebResponse** к типу **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cb055-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="cb055-110">Платформа .NET Framework также предоставляет классы <xref:System.Net.FileWebRequest> и <xref:System.Net.FileWebResponse> для обработки запросов ресурсов, использующих схему URI "file:".</span><span class="sxs-lookup"><span data-stu-id="cb055-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="cb055-111">Аналогичным образом, классы <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse> используются для обработки запросов ресурсов, использующих схему "ftp:".</span><span class="sxs-lookup"><span data-stu-id="cb055-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="cb055-112">Если вы выполняете запросы к ресурсу, использующему любую из этих схем, то можете получить объект, с помощью которого будет выполняться запрос, используя метод **WebRequest.Create**.</span><span class="sxs-lookup"><span data-stu-id="cb055-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="cb055-113">Для обработки запросов, использующих другие протоколы уровня приложений, необходимо реализовать классы для определенного протокола, производные от **WebRequest** и **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cb055-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="cb055-114">Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="cb055-114">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb055-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb055-115">See also</span></span>

- [<span data-ttu-id="cb055-116">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="cb055-116">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="cb055-117">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="cb055-117">Requesting Data</span></span>](requesting-data.md)
