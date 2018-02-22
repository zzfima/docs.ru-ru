---
title: "Безопасное хранение секретов приложения во время разработки"
description: "Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Безопасное хранение секретов приложения во время разработки"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f70f7c741da9653745e4f542125986c701b5d22d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="57962-104">Безопасное хранение секретов приложения во время разработки</span><span class="sxs-lookup"><span data-stu-id="57962-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="57962-105">Для подключения к защищенным ресурсам и другим службам приложения ASP.NET Core обычно используют строки подключения, пароли или другие учетные данные, содержащие конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="57962-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="57962-106">Эти конфиденциальные сведения называются *секреты*.</span><span class="sxs-lookup"><span data-stu-id="57962-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="57962-107">Рекомендуется не включать секреты в исходный код и ни в коем случае не хранить секреты в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="57962-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="57962-108">Лучше использовать модель конфигурации ASP.NET Core для чтения секретов из более безопасных мест.</span><span class="sxs-lookup"><span data-stu-id="57962-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="57962-109">Следует отличать секреты для доступа к ресурсам разработки и промежуточных процессов от секретов для доступа к производственным ресурсам, поскольку их используют разные пользователи.</span><span class="sxs-lookup"><span data-stu-id="57962-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="57962-110">Секреты, используемые на стадии разработки, как правило, хранятся в переменных среды или в менеджере секретов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="57962-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="57962-111">Для большей безопасности в рабочих средах микрослужбы могут хранить секреты в хранилище Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="57962-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="57962-112">Хранение секретов в переменных среды</span><span class="sxs-lookup"><span data-stu-id="57962-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="57962-113">Чтобы хранить секреты отдельно от исходного кода, разработчики могут установить строки секретов в качестве [переменных среды](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) на компьютерах, использующихся для разработки.</span><span class="sxs-lookup"><span data-stu-id="57962-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="57962-114">При использовании переменных среды для хранения секретов с иерархическими именами (которые вложены в разделы конфигурации) создайте имя для переменных среды, включающее полную иерархию имени секрета, разделенную двоеточием (:).</span><span class="sxs-lookup"><span data-stu-id="57962-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="57962-115">Например, если установить для переменной среды Logging:LogLevel:Default значение Debug, это будет равноценно значению конфигурации из следующего файла JSON:</span><span class="sxs-lookup"><span data-stu-id="57962-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="57962-116">Чтобы обратиться к этим значениям из переменных среды, приложению достаточно вызвать AddEnvironmentVariables в ConfigurationBuilder при создании объекта IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="57962-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="57962-117">Как правило, переменные среды хранятся в виде обычного текста, и если компьютер или процесс с этими переменными среды будут скомпрометированы, значения переменных среды будут видны.</span><span class="sxs-lookup"><span data-stu-id="57962-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="57962-118">Хранение секретов с помощью менеджера секретов ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="57962-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="57962-119">[Менеджер секретов](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) ASP.NET Core — это еще один инструмент для хранения секретов отдельно от исходного кода.</span><span class="sxs-lookup"><span data-stu-id="57962-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="57962-120">Чтобы использовать менеджер секретов, включите ссылку на инструмент (DotNetCliToolReference) в пакет Microsoft.Extensions.SecretManager.Tools в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="57962-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="57962-121">После назначения и восстановления этой зависимости можно установить значение секретов в командной строке с помощью команды dotnet user-secrets.</span><span class="sxs-lookup"><span data-stu-id="57962-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="57962-122">Секреты будут храниться в файле JSON в каталоге профилей пользователей (в зависимости от ОС), отдельно от исходного кода.</span><span class="sxs-lookup"><span data-stu-id="57962-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="57962-123">Секреты, заданные менеджером секретов, упорядочиваются свойством UserSecretsId в проекте, использующем эти секреты.</span><span class="sxs-lookup"><span data-stu-id="57962-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="57962-124">Поэтому обязательно задайте свойство UserSecretsId в файле проекта (как показано ниже во фрагменте кода).</span><span class="sxs-lookup"><span data-stu-id="57962-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="57962-125">Строка, используемая в качестве идентификатора, не важна, если она уникальна для проекта.</span><span class="sxs-lookup"><span data-stu-id="57962-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="57962-126">Секреты, хранящиеся в менеджере секретов, используются в приложении путем вызова AddUserSecrets&lt;T&gt; в экземпляре ConfigurationBuilder, чтобы включить секреты приложения в его конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="57962-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="57962-127">Общий параметр T должен обозначать тип в сборке, к которой применяется UserSecretId.</span><span class="sxs-lookup"><span data-stu-id="57962-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="57962-128">Как правило, можно использовать AddUserSecrets&lt;Startup&gt;.</span><span class="sxs-lookup"><span data-stu-id="57962-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="57962-129">[Назад] (authorization-net-microservices-web-applications.md) [Далее] (azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="57962-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
