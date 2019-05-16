---
title: Загрузка пакета проверки реестра имен поставщиков
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 5684844f1db33b075df099b3026d9d0c1061199f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631851"
---
# <a name="download-the-validating-issuer-name-registry-package"></a><span data-ttu-id="da95e-102">Загрузка пакета проверки реестра имен поставщиков</span><span class="sxs-lookup"><span data-stu-id="da95e-102">Download the Validating Issuer Name Registry Package</span></span>

<span data-ttu-id="da95e-103">В этом разделе демонстрируется, как скачать и использовать средство проверки реестра имен поставщиков (VINR) в проекте.</span><span class="sxs-lookup"><span data-stu-id="da95e-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>

<span data-ttu-id="da95e-104">Средство VINR распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки.</span><span class="sxs-lookup"><span data-stu-id="da95e-104">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="da95e-105">Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](https://nuget.org) и выполните установку.</span><span class="sxs-lookup"><span data-stu-id="da95e-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="da95e-106">Можно просмотреть историю версий для расширения, посетив его страницу в NuGet: [Microsoft, проверка реестра имен поставщиков в NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="da95e-106">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="da95e-107">С помощью графического интерфейса диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="da95e-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="da95e-108">В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="da95e-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="da95e-109">В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `ValidatingIssuerNameRegistry` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="da95e-109">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>

3. <span data-ttu-id="da95e-110">В области результатов нажмите кнопку **Установить** для первого результата.</span><span class="sxs-lookup"><span data-stu-id="da95e-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="da95e-111">Начнется скачивание пакета.</span><span class="sxs-lookup"><span data-stu-id="da95e-111">The package will begin downloading.</span></span> <span data-ttu-id="da95e-112">Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения".</span><span class="sxs-lookup"><span data-stu-id="da95e-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="da95e-113">Если вы согласны с условиями лицензии, щелкните **Я принимаю**.</span><span class="sxs-lookup"><span data-stu-id="da95e-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="da95e-114">Последние версии сборок VINR скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="da95e-114">The latest VINR assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="da95e-115">Использование консоли диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="da95e-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="da95e-116">В Visual Studio щелкните **средства** > **диспетчер пакетов NuGet** > **консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="da95e-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="da95e-117">Откроется окно **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="da95e-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="da95e-118">Введите следующий текст и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="da95e-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. <span data-ttu-id="da95e-119">Последние версии сборок VINR скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="da95e-119">The latest VINR assemblies will be downloaded and added to your project.</span></span>
