---
title: Загрузка пакета обработчика веб-токенов JSON
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792760"
---
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="fa81b-102">Скачать пакет обработчика токенов JSON Web</span><span class="sxs-lookup"><span data-stu-id="fa81b-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="fa81b-103">В этом разделе описывается скачивание и использование обработчика веб-токенов JSON в проекте.</span><span class="sxs-lookup"><span data-stu-id="fa81b-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="fa81b-104">Обработчик веб-токенов JSON распространяется в виде пакета NuGet, который добавляет в проект необходимые ссылки и сборки.</span><span class="sxs-lookup"><span data-stu-id="fa81b-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="fa81b-105">Если вы еще не установили NuGet, перейдите на веб-сайт [nuget.org](https://nuget.org) и выполните установку.</span><span class="sxs-lookup"><span data-stu-id="fa81b-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="fa81b-106">Можно просмотреть историю версий для расширения, посетив его страницу в NuGet: [Обработчик веб-токенов JSON в NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span><span class="sxs-lookup"><span data-stu-id="fa81b-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="fa81b-107">С помощью графического интерфейса диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="fa81b-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="fa81b-108">В Visual Studio щелкните правой кнопкой мыши проект в **обозревателе решений**, а затем выберите **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="fa81b-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="fa81b-109">В окне **Управление пакетами NuGet** щелкните в поле поиска, введите `JWT Token Handler` и нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="fa81b-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="fa81b-110">В области результатов нажмите кнопку **Установить** для первого результата.</span><span class="sxs-lookup"><span data-stu-id="fa81b-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="fa81b-111">Начнется скачивание пакета.</span><span class="sxs-lookup"><span data-stu-id="fa81b-111">The package will begin downloading.</span></span> <span data-ttu-id="fa81b-112">Перед его добавлением в проект появится диалоговое окно "Принятие условий лицензионного соглашения".</span><span class="sxs-lookup"><span data-stu-id="fa81b-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="fa81b-113">Если вы согласны с условиями лицензии, щелкните **Я принимаю**.</span><span class="sxs-lookup"><span data-stu-id="fa81b-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="fa81b-114">Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="fa81b-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="fa81b-115">Использование консоли диспетчера пакетов</span><span class="sxs-lookup"><span data-stu-id="fa81b-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="fa81b-116">В Visual Studio щелкните **средства** > **диспетчер пакетов NuGet** > **консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="fa81b-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="fa81b-117">Откроется окно **Консоль диспетчера пакетов**.</span><span class="sxs-lookup"><span data-stu-id="fa81b-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="fa81b-118">Введите следующий текст и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="fa81b-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="fa81b-119">Последние версии сборок обработчика веб-токенов JSON скачиваются и добавляются в проект.</span><span class="sxs-lookup"><span data-stu-id="fa81b-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>