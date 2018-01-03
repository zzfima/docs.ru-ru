---
title: "Загрузка пакета обработчика веб-токенов JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5982830404d8d8780bf41153741928b68dc5c7d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-json-web-token-handler-package"></a><span data-ttu-id="eec77-102">Загрузка пакета обработчика веб-токенов JSON</span><span class="sxs-lookup"><span data-stu-id="eec77-102">Downloading the JSON Web Token Handler Package</span></span>
<span data-ttu-id="eec77-103">В этом разделе описывается скачивание и использование обработчика веб-токенов JSON в проекте.</span><span class="sxs-lookup"><span data-stu-id="eec77-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>  
  
## <a name="downloading-the-json-web-token-handler"></a><span data-ttu-id="eec77-104">Загрузка обработчика веб-токенов JSON</span><span class="sxs-lookup"><span data-stu-id="eec77-104">Downloading the JSON Web Token Handler</span></span>  
 <span data-ttu-id="eec77-105">Обработчик веб-токенов JSON распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки.</span><span class="sxs-lookup"><span data-stu-id="eec77-105">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="eec77-106">Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](http://nuget.org) и выполните установку.</span><span class="sxs-lookup"><span data-stu-id="eec77-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="eec77-107">Чтобы просмотреть историю версий этого расширения, перейдите на соответствующую страницу на веб-сайте NuGet: [Обработчик веб-токенов JSON](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span><span class="sxs-lookup"><span data-stu-id="eec77-107">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a><span data-ttu-id="eec77-108">Скачивание обработчика веб-токенов JSON с помощью графического пользовательского интерфейса диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="eec77-108">Downloading the JSON Web Token Handler by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="eec77-109">В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="eec77-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="eec77-110">В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `JWT Token Handler` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="eec77-110">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="eec77-111">В области результатов нажмите кнопку **Установить** для первого результата.</span><span class="sxs-lookup"><span data-stu-id="eec77-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="eec77-112">Начнется скачивание пакета.</span><span class="sxs-lookup"><span data-stu-id="eec77-112">The package will begin downloading.</span></span> <span data-ttu-id="eec77-113">Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения".</span><span class="sxs-lookup"><span data-stu-id="eec77-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="eec77-114">Если вы согласны с условиями лицензии, щелкните **Я принимаю**.</span><span class="sxs-lookup"><span data-stu-id="eec77-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="eec77-115">Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="eec77-115">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a><span data-ttu-id="eec77-116">Скачивание обработчика веб-токенов JSON с помощью консоли диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="eec77-116">Downloading the JSON Web Token Handler by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="eec77-117">В Visual Studio щелкните **Сервис**, **Диспетчер пакетов библиотеки** и выберите **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="eec77-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="eec77-118">Откроется окно **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="eec77-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="eec77-119">Введите следующий текст и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="eec77-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  <span data-ttu-id="eec77-120">Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="eec77-120">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
