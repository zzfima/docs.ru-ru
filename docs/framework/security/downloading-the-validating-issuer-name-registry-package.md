---
title: Загрузка пакета проверки реестра имен поставщиков
ms.date: 03/30/2017
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 03b68f4b9dc6fde02c951968067e0311e4981d33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398753"
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="6b70f-102">Загрузка пакета проверки реестра имен поставщиков</span><span class="sxs-lookup"><span data-stu-id="6b70f-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="6b70f-103">В этом разделе демонстрируется, как скачать и использовать средство проверки реестра имен поставщиков (VINR) в проекте.</span><span class="sxs-lookup"><span data-stu-id="6b70f-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="6b70f-104">Скачивание средства проверки реестра имен поставщиков</span><span class="sxs-lookup"><span data-stu-id="6b70f-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="6b70f-105">Средство VINR распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки.</span><span class="sxs-lookup"><span data-stu-id="6b70f-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="6b70f-106">Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](http://nuget.org) и выполните установку.</span><span class="sxs-lookup"><span data-stu-id="6b70f-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="6b70f-107">Чтобы просмотреть историю версий этого расширения, перейдите на соответствующую страницу на веб-сайте NuGet: [Средство проверки реестра имен поставщиков Майкрософт](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="6b70f-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="6b70f-108">Скачивание средства проверки реестра имен поставщиков с помощью графического пользовательского интерфейса диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="6b70f-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="6b70f-109">В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="6b70f-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="6b70f-110">В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `ValidatingIssuerNameRegistry` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="6b70f-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="6b70f-111">В области результатов нажмите кнопку **Установить** для первого результата.</span><span class="sxs-lookup"><span data-stu-id="6b70f-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="6b70f-112">Начнется скачивание пакета.</span><span class="sxs-lookup"><span data-stu-id="6b70f-112">The package will begin downloading.</span></span> <span data-ttu-id="6b70f-113">Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения".</span><span class="sxs-lookup"><span data-stu-id="6b70f-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="6b70f-114">Если вы согласны с условиями лицензии, щелкните **Я принимаю**.</span><span class="sxs-lookup"><span data-stu-id="6b70f-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="6b70f-115">Последние версии сборок VINR скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="6b70f-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="6b70f-116">Скачивание средства проверки реестра имен поставщиков с помощью консоли диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="6b70f-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="6b70f-117">В Visual Studio щелкните **Сервис**, **Диспетчер пакетов библиотеки** и выберите **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="6b70f-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="6b70f-118">Откроется окно **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="6b70f-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="6b70f-119">Введите следующий текст и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="6b70f-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="6b70f-120">Последние версии сборок VINR скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="6b70f-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
