---
title: Практическое руководство. Присвоение данных пользователя групповым подключениям
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
ms.openlocfilehash: 6d0be3ccfc0a0b4b032283b7ed34908f79774bb6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50049546"
---
# <a name="how-to-assign-user-information-to-group-connections"></a><span data-ttu-id="b368d-102">Практическое руководство. Присвоение данных пользователя групповым подключениям</span><span class="sxs-lookup"><span data-stu-id="b368d-102">How to: Assign User Information to Group Connections</span></span>

  
 <span data-ttu-id="b368d-103">В следующем примере демонстрируется, как присвоить данные пользователя групповым подключениям. В этом разделе предполагается, что приложение присвоило значения переменным *UserName*, *SecurelyStoredPassword* и *Domain* до вызова этого раздела кода, а переменная *UserName* является уникальной.</span><span class="sxs-lookup"><span data-stu-id="b368d-103">The following example demonstrates how to assign user information to group connections, assuming that the application sets the variables *UserName*, *SecurelyStoredPassword*, and *Domain* before this section of code is called and that *UserName* is unique.</span></span>  
  
### <a name="to-assign-user-information-to-a-group-connection"></a><span data-ttu-id="b368d-104">Присвоение данных пользователя групповому подключению</span><span class="sxs-lookup"><span data-stu-id="b368d-104">To assign user information to a group connection</span></span>  
  
1.  <span data-ttu-id="b368d-105">Создайте имя группы подключений.</span><span class="sxs-lookup"><span data-stu-id="b368d-105">Create a connection group name.</span></span>  
  
    ```csharp  
    SHA1Managed Sha1 = new SHA1Managed();  
    Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
    String secureGroupName = Encoding.Default.GetString(updHash);  
    ```  
  
    ```vb  
    Dim Sha1 As New SHA1Managed()  
    Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
    Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
    ```  
  
2.  <span data-ttu-id="b368d-106">Создайте запрос к конкретному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b368d-106">Create a request for a specific URL.</span></span> <span data-ttu-id="b368d-107">Например, следующий код создает запрос к URL-адресу `http://www.contoso.com.`</span><span class="sxs-lookup"><span data-stu-id="b368d-107">For example, the following code creates a request for the URL `http://www.contoso.com.`</span></span>  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3.  <span data-ttu-id="b368d-108">Задайте учетные данные и имя группы подключений для веб-запроса и вызовите метод **GetResponse**, чтобы получить объект **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="b368d-108">Set the credentials and Connection GroupName for the Web request, and call **GetResponse** to retrieve a **WebResponse** object.</span></span>  
  
    ```csharp  
    myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
    myWebRequest.ConnectionGroupName = secureGroupName;  
  
    WebResponse myWebResponse=myWebRequest.GetResponse();  
    ```  
  
    ```vb  
    myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
    myWebRequest.ConnectionGroupName = secureGroupName  
  
    Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
    ```  
  
4.  <span data-ttu-id="b368d-109">После использования объекта WebRespose закройте поток ответа.</span><span class="sxs-lookup"><span data-stu-id="b368d-109">Close the response stream after using the WebRespose object.</span></span>  
  
    ```csharp  
    MyWebResponse.Close();  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 <span data-ttu-id="b368d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b368d-110">Example</span></span>  
  
```csharp  
// Create a connection group name.  
SHA1Managed Sha1 = new SHA1Managed();  
Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
String secureGroupName = Encoding.Default.GetString(updHash);  
  
// Create a request for a specific URL.  
WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
  
myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
myWebRequest.ConnectionGroupName = secureGroupName;  
  
WebResponse myWebResponse=myWebRequest.GetResponse();  
  
// Insert the code that uses myWebResponse.  
  
MyWebResponse.Close();  
```  
  
```vb  
' Create a secure group name.  
Dim Sha1 As New SHA1Managed()  
Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
  
' Create a request for a specific URL.  
Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
  
myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
myWebRequest.ConnectionGroupName = secureGroupName  
  
Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
' Insert the code that uses myWebResponse.  
MyWebResponse.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b368d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b368d-111">See Also</span></span>  
 [<span data-ttu-id="b368d-112">Управление подключениями</span><span class="sxs-lookup"><span data-stu-id="b368d-112">Managing Connections</span></span>](../../../docs/framework/network-programming/managing-connections.md)  
 [<span data-ttu-id="b368d-113">Группирование подключений</span><span class="sxs-lookup"><span data-stu-id="b368d-113">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)
