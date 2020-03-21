---
title: Использование средств разработки WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183083"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="66cfc-102">Использование средств разработки WCF</span><span class="sxs-lookup"><span data-stu-id="66cfc-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="66cfc-103">В этом разделе описаны инструменты разработки Visual Studio, которые могут помочь вам в разработке WCFservice.</span><span class="sxs-lookup"><span data-stu-id="66cfc-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="66cfc-104">Вы можете использовать шаблоны Visual Studio в качестве основы для быстрого создания собственного сервиса, а затем использовать WCF Service Auto Host и WCF Test Client для отладки и тестирования сервиса.</span><span class="sxs-lookup"><span data-stu-id="66cfc-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="66cfc-105">Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.</span><span class="sxs-lookup"><span data-stu-id="66cfc-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="66cfc-106">Начиная с Visual Studio 2017, инструменты разработки WCF не устанавливаются по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66cfc-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="66cfc-107">Для использования этих функций необходимо убедиться, что компонент Windows Communication Foundation выбран в установке Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66cfc-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="66cfc-108">Инструменты разработчика WCF</span><span class="sxs-lookup"><span data-stu-id="66cfc-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="66cfc-109">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66cfc-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="66cfc-110">Вы можете использовать предопределенные visual Studio проект и шаблоны элементов в Visual Studio для быстрого создания wCF-сервисов и окружающих приложений.</span><span class="sxs-lookup"><span data-stu-id="66cfc-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="66cfc-111">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="66cfc-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="66cfc-112">Автохост WCF Service Auto Host (WcfSvcHost.exe) позволяет запустить Visual Studio-отладчик (F5) для автоматического размещения и тестирования услуги, которая была реализована.</span><span class="sxs-lookup"><span data-stu-id="66cfc-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="66cfc-113">Затем вы можете протестировать сервис с помощью испытательного клиента WCF (wcfTestClient.exe) или собственного клиента, чтобы найти и исправить любые потенциальные ошибки.</span><span class="sxs-lookup"><span data-stu-id="66cfc-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="66cfc-114">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="66cfc-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="66cfc-115">WCF Test Client (WcfTestClient.exe) — это инструмент GUI, позволяющий ввести параметры произвольных типов, представить этот вход в службу и просмотреть ответ службы.</span><span class="sxs-lookup"><span data-stu-id="66cfc-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="66cfc-116">Он обеспечивает бесшовный опыт тестирования службы в сочетании с WCF Сервис Автохост.</span><span class="sxs-lookup"><span data-stu-id="66cfc-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="66cfc-117">Формирование классов типов данных из XML</span><span class="sxs-lookup"><span data-stu-id="66cfc-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="66cfc-118">Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="66cfc-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="66cfc-119">Классы, определенные в данных, будут преобразованы в типы кода.</span><span class="sxs-lookup"><span data-stu-id="66cfc-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="66cfc-120">Использование инструментов без прав администратора</span><span class="sxs-lookup"><span data-stu-id="66cfc-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="66cfc-121">Для того, чтобы пользователи, не имеющие привилегий администратора, могли разрабатывать сервисы WCF, во время установки Visual Studio создается ACL (Список управления доступом) для пространства имен «http://+:8731/Design_Time_Addressesво время установки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66cfc-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="66cfc-122">Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему.</span><span class="sxs-lookup"><span data-stu-id="66cfc-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="66cfc-123">Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="66cfc-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="66cfc-124">Он также позволяет пользователям использовать WCF Сервис Авто Хост (wcfSvcHost.exe) без предоставления им привилегий администратора.</span><span class="sxs-lookup"><span data-stu-id="66cfc-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="66cfc-125">Вы можете изменить доступ с помощью инструмента Netsh.exe в Windows Vista под учетной записью повышенной администратора.</span><span class="sxs-lookup"><span data-stu-id="66cfc-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="66cfc-126">Ниже приведен пример использования средства Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="66cfc-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="66cfc-127">Для получения дополнительной информации о Netsh.exe, [см.](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="66cfc-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66cfc-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66cfc-128">See also</span></span>

- [<span data-ttu-id="66cfc-129">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="66cfc-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="66cfc-130">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="66cfc-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="66cfc-131">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="66cfc-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
