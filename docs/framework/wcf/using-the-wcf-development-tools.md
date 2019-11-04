---
title: Использование средств разработки WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: afa62a63aa955dc868791da635418331f93e9e87
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420680"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="9f144-102">Использование средств разработки WCF</span><span class="sxs-lookup"><span data-stu-id="9f144-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="9f144-103">В этом разделе описываются средства разработки Visual Studio, которые помогут вам в разработке WCFservice.</span><span class="sxs-lookup"><span data-stu-id="9f144-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="9f144-104">Вы можете использовать шаблоны Visual Studio в качестве основы для быстрого создания собственной службы, а затем для отладки и тестирования службы использовать автоматическое размещение службы WCF и клиент тестов WCF.</span><span class="sxs-lookup"><span data-stu-id="9f144-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="9f144-105">Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.</span><span class="sxs-lookup"><span data-stu-id="9f144-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
 
 > [!NOTE]
 > <span data-ttu-id="9f144-106">Начиная с Visual Studio 2017 средства разработки WCF по умолчанию не устанавливаются.</span><span class="sxs-lookup"><span data-stu-id="9f144-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="9f144-107">Чтобы использовать эти функции, необходимо убедиться в том, что в установщике Visual Studio выбран компонент Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="9f144-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="9f144-108">Инструменты разработчика WCF</span><span class="sxs-lookup"><span data-stu-id="9f144-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="9f144-109">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f144-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="9f144-110">Вы можете использовать стандартные шаблоны проектов и элементов Visual Studio в Visual Studio для быстрой сборки служб WCF и окружающих приложений.</span><span class="sxs-lookup"><span data-stu-id="9f144-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="9f144-111">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9f144-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="9f144-112">Автоматическое размещение службы WCF (WcfSvcHost. exe) позволяет запустить отладчик Visual Studio (F5) для автоматического размещения и тестирования реализованной службы.</span><span class="sxs-lookup"><span data-stu-id="9f144-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="9f144-113">Затем можно протестировать службу с помощью тестового клиента WCF (клиент WcfTestClient. exe) или собственного клиента, чтобы найти и исправить возможные ошибки.</span><span class="sxs-lookup"><span data-stu-id="9f144-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="9f144-114">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9f144-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="9f144-115">Тестовый клиент WCF (клиент WcfTestClient. exe) — это средство графического пользовательского интерфейса, которое позволяет вводить параметры произвольных типов, отправлять эти входные данные в службу и просматривать ответ, отправляемый службой обратно.</span><span class="sxs-lookup"><span data-stu-id="9f144-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="9f144-116">Она обеспечивает простой процесс тестирования служб при объединении с автоматическим размещением службы WCF.</span><span class="sxs-lookup"><span data-stu-id="9f144-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="9f144-117">Формирование классов типов данных из XML</span><span class="sxs-lookup"><span data-stu-id="9f144-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="9f144-118">Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="9f144-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="9f144-119">Классы, определенные в данных, будут преобразованы в типы кода.</span><span class="sxs-lookup"><span data-stu-id="9f144-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="9f144-120">Использование инструментов без прав администратора</span><span class="sxs-lookup"><span data-stu-id="9f144-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="9f144-121">Чтобы разрешить пользователям без прав администратора для разработки служб WCF, в ходе установки Visual Studio для пространства имен "http://+:8731/Design_Time_Addresses" создается список управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="9f144-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="9f144-122">Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему.</span><span class="sxs-lookup"><span data-stu-id="9f144-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="9f144-123">Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f144-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="9f144-124">Он также позволяет пользователям использовать автоматическое размещение службы WCF (wcfSvcHost. exe) без предоставления прав администратора.</span><span class="sxs-lookup"><span data-stu-id="9f144-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="9f144-125">Можно изменить доступ используя средство Netsh.exe в [!INCLUDE[wv](../../../includes/wv-md.md)] под учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="9f144-125">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="9f144-126">Ниже приведен пример использования средства Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="9f144-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="9f144-127">Дополнительные сведения о программе Netsh. exe см. в разделе [Использование средства Netsh. exe и параметров командной строки](https://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="9f144-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f144-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9f144-128">See also</span></span>

- [<span data-ttu-id="9f144-129">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f144-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="9f144-130">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9f144-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="9f144-131">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9f144-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
