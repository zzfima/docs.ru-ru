---
title: Файл ReadMe для образца проверки подлинности с расширенной защитой
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 53592db03c88e673d529ef04f2fbc6e182897457
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319356"
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="93e2a-102">Файл ReadMe для образца проверки подлинности с расширенной защитой</span><span class="sxs-lookup"><span data-stu-id="93e2a-102">ReadMe for Extended Protection Authentication Sample</span></span>
<span data-ttu-id="93e2a-103">Расширенная защита-это технология безопасности для защиты от атак man-in--middle (MITM), в которых злоумышленник («man-in--middle»), перехватывает учетных данных клиента и использует их для доступа к защищенным ресурсам на сервере предполагаемый клиента.</span><span class="sxs-lookup"><span data-stu-id="93e2a-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>  
  
 <span data-ttu-id="93e2a-104">Дополнительные сведения см. в разделе [расширенная защита для проверки подлинности Обзор](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span><span class="sxs-lookup"><span data-stu-id="93e2a-104">For more information, see [Extended Protection for Authentication Overview](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93e2a-105">Этот образец работает только в случае размещения в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="93e2a-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="93e2a-106">Он не работает на сервере разработки Visual Studio, поскольку этот сервер не поддерживает HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93e2a-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="93e2a-107">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="93e2a-107">To Set Up, Build, and Run the Sample</span></span>  
  
1. <span data-ttu-id="93e2a-108">Установите службы IIS на компьютер из Установка и удаление программ -> компоненты Windows.</span><span class="sxs-lookup"><span data-stu-id="93e2a-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>  
  
2. <span data-ttu-id="93e2a-109">Включите проверку подлинности Windows в функции Windows: Службы IIS "->" World Wide Web Services -> Безопасность -> Проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="93e2a-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>  
  
3. <span data-ttu-id="93e2a-110">Включите активацию HTTP в функции Windows: Microsoft .NET Framework 3.5.1 -> активация Windows Communication Foundation HTTP.</span><span class="sxs-lookup"><span data-stu-id="93e2a-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>  
  
4. <span data-ttu-id="93e2a-111">Для работы этого образца клиенту необходимо установить защищенный канал с сервером, для чего требуется наличие сертификата сервера, который может устанавливаться из диспетчера служб IIS.</span><span class="sxs-lookup"><span data-stu-id="93e2a-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="93e2a-112">Откройте диспетчер служб IIS "->" сертификаты сервера (из вкладки представления компонентов).</span><span class="sxs-lookup"><span data-stu-id="93e2a-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>  
  
    2.  <span data-ttu-id="93e2a-113">Для тестирования этого образца можно создать самозаверяющий сертификат.</span><span class="sxs-lookup"><span data-stu-id="93e2a-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="93e2a-114">(Чтобы не выводить в Internet Explorer запрос об отсутствии защиты сертификата, можно установить его в хранилище «Доверенные корневые центры сертификации».)</span><span class="sxs-lookup"><span data-stu-id="93e2a-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>  
  
5. <span data-ttu-id="93e2a-115">Перейдите в область «Действия» для веб-узла по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="93e2a-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="93e2a-116">Щелкните "Изменить" сайт -> привязки.</span><span class="sxs-lookup"><span data-stu-id="93e2a-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="93e2a-117">Добавьте тип HTTPS, если он отсутствует, указав номер порта 443, и назначьте SSL-сертификат, созданный на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="93e2a-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>  
  
6. <span data-ttu-id="93e2a-118">Постройте службу.</span><span class="sxs-lookup"><span data-stu-id="93e2a-118">Build the service.</span></span> <span data-ttu-id="93e2a-119">В службах IIS будет создан виртуальный каталог (из действия после построения, указанного в свойствах проекта) и скопированы DLL-файлы, SVC-файлы и файлы конфигурации, необходимые для размещения службы в Интернете.</span><span class="sxs-lookup"><span data-stu-id="93e2a-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>  
  
7. <span data-ttu-id="93e2a-120">Откройте диспетчер служб IIS.</span><span class="sxs-lookup"><span data-stu-id="93e2a-120">Open the IIS Manager.</span></span> <span data-ttu-id="93e2a-121">Щелкните правой кнопкой мыши виртуальный каталог (ExtendedProtection), созданный на предыдущем шаге, и выберите команду «Преобразовать в приложение».</span><span class="sxs-lookup"><span data-stu-id="93e2a-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>  
  
8. <span data-ttu-id="93e2a-122">Откройте модуль проверки подлинности в диспетчере служб IIS для этого виртуального каталога и включите проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="93e2a-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>  
  
9. <span data-ttu-id="93e2a-123">Откройте дополнительные параметры проверки подлинности Windows для этого виртуального каталога и установите для нее значение «Требуется», поскольку в образце соответствующий параметр ExtendedProtection имеет значение «Всегда».</span><span class="sxs-lookup"><span data-stu-id="93e2a-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>  
  
10. <span data-ttu-id="93e2a-124">Проверить работу службы можно, обратившись по URL-адресу из окна браузера.</span><span class="sxs-lookup"><span data-stu-id="93e2a-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="93e2a-125">Чтобы получить доступ к этому URL-адресу с другого компьютера, убедитесь, что в брандмауэре открыты все входящие подключения HTTP и HTTPS.</span><span class="sxs-lookup"><span data-stu-id="93e2a-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>  
  
11. <span data-ttu-id="93e2a-126">Откройте файл конфигурации клиента и укажите полное имя компьютера для \<клиента >- \<endpoint >-атрибут адреса, заменив << full_machine_name >>.</span><span class="sxs-lookup"><span data-stu-id="93e2a-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing <<full_machine_name>>.</span></span>  
  
12. <span data-ttu-id="93e2a-127">Запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="93e2a-127">Run the client.</span></span> <span data-ttu-id="93e2a-128">Клиент обменивается данными со службой, устанавливая защищенный канал и используя расширенную защиту не базе канала.</span><span class="sxs-lookup"><span data-stu-id="93e2a-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
