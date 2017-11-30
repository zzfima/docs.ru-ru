---
title: "Безопасно хранить секреты приложения во время разработки"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Безопасно хранить секреты приложения во время разработки"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="b6f5d-104">Безопасно хранить секреты приложения во время разработки</span><span class="sxs-lookup"><span data-stu-id="b6f5d-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="b6f5d-105">Для подключения к защищенным ресурсам и других служб, приложений ASP.NET Core обычно требуется использовать строки подключения, пароли или другие учетные данные, содержащие конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="b6f5d-106">Эти фрагменты конфиденциальные сведения, называются *секреты*.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="b6f5d-107">Рекомендуется не включать секретные данные в исходном коде и определенно не для хранения конфиденциальных данных в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="b6f5d-108">Вместо этого следует использовать модель конфигурации ASP.NET Core из которого выполняется чтение секреты более безопасных расположениях.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="b6f5d-109">Следует отличать секретные данные, для доступа к разработки и размещения, ресурсы из тех, которые используются для доступа к ресурсам производственной, так как разные люди, потребуется доступ к эти разные наборы секретные данные.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="b6f5d-110">Хранить секретные данные, используемые во время разработки, должны либо хранить секреты в переменных среды или при помощи ASP.NET Core секрет диспетчера типичные подходы.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="b6f5d-111">Для более безопасного хранения в производственных средах микрослужбами можно хранить секреты в хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="b6f5d-112">Сохранение секретов в переменных среды</span><span class="sxs-lookup"><span data-stu-id="b6f5d-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="b6f5d-113">Один из способов хранить секреты из исходного кода предназначено для разработчиков задать секретные данные на основе строк как [переменных среды](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) на своих компьютерах для разработки.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="b6f5d-114">При использовании переменных среды для хранения конфиденциальных данных с иерархические имена (которые вложены в разделы конфигурации), создайте имя для переменных среды, включающее полную иерархию имя секрета разделенные двоеточием (:).</span><span class="sxs-lookup"><span data-stu-id="b6f5d-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="b6f5d-115">Например установив переменную среды ведения журнала: LogLevel:Default для отладки будет равно значению конфигурации из файла JSON:</span><span class="sxs-lookup"><span data-stu-id="b6f5d-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="b6f5d-116">Чтобы открыть эти значения из переменных среды, просто приложению вызывать AddEnvironmentVariables его ConfigurationBuilder при создании объекта IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="b6f5d-117">Обратите внимание, что переменные среды обычно хранятся в виде обычного текста, таким образом, в случае компрометации компьютера или процесс с переменными среды, значения переменных среды видимым.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="b6f5d-118">Сохранение секретов, с помощью диспетчера секрет ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6f5d-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="b6f5d-119">ASP.NET Core [Manager секрет](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) средство обеспечивает сохранение секретов из исходного кода в другой метод.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="b6f5d-120">Использование диспетчера секрет, включаемых Справочник по средствам (DotNetCliToolReference) Microsoft.Extensions.SecretManager.Tools пакета в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="b6f5d-121">После этой зависимости и был восстановлен, команда секретов пользователя dotnet может использоваться для присвоения секретные данные из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="b6f5d-122">Эти секретные данные будут храниться в файле JSON в каталоге профиля пользователя (сведения зависят от операционной системы), от исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="b6f5d-123">Секретные данные, заданные секрет диспетчера организованы по UserSecretsId свойства проекта, который использует секреты.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="b6f5d-124">Таким образом необходимо убедиться, что свойство UserSecretsId задать в файле проекта (как показано в приведенном ниже фрагменте кода).</span><span class="sxs-lookup"><span data-stu-id="b6f5d-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="b6f5d-125">Строка используется в качестве идентификатора не имеет значения, пока он уникален в проекте.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="b6f5d-126">С помощью секретные данные, хранящиеся в приложении с помощью диспетчера секрет достигается посредством вызова AddUserSecrets&lt;T&gt; на экземпляре ConfigurationBuilder для включения секретные данные приложения в его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="b6f5d-127">Общий параметр T должен быть тип в сборке, которая UserSecretId была применена к.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="b6f5d-128">Обычно с помощью AddUserSecrets&lt;запуска&gt; нормально.</span><span class="sxs-lookup"><span data-stu-id="b6f5d-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b6f5d-129">[Предыдущие] (авторизации net микрослужбами web-applications.md) [Далее] (azure-key хранилище — защищает secrets.md)</span><span class="sxs-lookup"><span data-stu-id="b6f5d-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
