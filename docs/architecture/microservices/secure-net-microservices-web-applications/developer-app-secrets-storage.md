---
title: Безопасное хранение секретов приложения во время разработки
description: Безопасность в микрослужбах .NET и веб-приложениях. Не храните секреты приложения, такие как пароли, строки подключения или ключи API, в системе управления версиями. Изучите параметры, которые можно использовать в ASP.NET Core, в частности, как обрабатывать пользовательские секреты.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501801"
---
# <a name="store-application-secrets-safely-during-development"></a><span data-ttu-id="57ee8-103">Безопасное хранение секретов приложения во время разработки</span><span class="sxs-lookup"><span data-stu-id="57ee8-103">Store application secrets safely during development</span></span>

<span data-ttu-id="57ee8-104">Для подключения к защищенным ресурсам и другим службам приложения ASP.NET Core обычно используют строки подключения, пароли или другие учетные данные, содержащие конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="57ee8-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="57ee8-105">Эти конфиденциальные сведения называются *секреты*.</span><span class="sxs-lookup"><span data-stu-id="57ee8-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="57ee8-106">Мы рекомендуем не включать секреты в исходный код и ни в коем случае не хранить секреты в системе управления версиями.</span><span class="sxs-lookup"><span data-stu-id="57ee8-106">It's a best practice to not include secrets in source code and making sure not to store secrets in source control.</span></span> <span data-ttu-id="57ee8-107">Лучше использовать модель конфигурации ASP.NET Core для чтения секретов из более безопасных мест.</span><span class="sxs-lookup"><span data-stu-id="57ee8-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="57ee8-108">Следует отличать секреты для доступа к ресурсам в среде разработки и промежуточной среде от секретов для доступа к ресурсам в рабочей среде. Это разные наборы секретов, которые используют разные пользователи.</span><span class="sxs-lookup"><span data-stu-id="57ee8-108">You must separate the secrets for accessing development and staging resources from the ones used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="57ee8-109">Секреты, используемые на стадии разработки, как правило, хранятся в переменных среды или в менеджере секретов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="57ee8-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="57ee8-110">Для большей безопасности в рабочих средах микрослужбы могут хранить секреты в хранилище Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="57ee8-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="store-secrets-in-environment-variables"></a><span data-ttu-id="57ee8-111">Хранение секретов в переменных среды</span><span class="sxs-lookup"><span data-stu-id="57ee8-111">Store secrets in environment variables</span></span>

<span data-ttu-id="57ee8-112">Чтобы хранить секреты отдельно от исходного кода, разработчики могут установить строки секретов в качестве [переменных среды](/aspnet/core/security/app-secrets#environment-variables) на компьютерах, использующихся для разработки.</span><span class="sxs-lookup"><span data-stu-id="57ee8-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="57ee8-113">При использовании переменных среды для хранения секретов с иерархическими именами, например, вложенными в разделы конфигурации, необходимо создать имя для переменных среды, чтобы включить полную иерархию разделов, разделенных двоеточием (:).</span><span class="sxs-lookup"><span data-stu-id="57ee8-113">When you use environment variables to store secrets with hierarchical names, such as the ones nested in configuration sections, you must name the variables to include the complete hierarchy of its sections, delimited with colons (:).</span></span>

<span data-ttu-id="57ee8-114">Например, если установить для переменной среды `Logging:LogLevel:Default` значение `Debug`, это будет соответствовать конфигурации из следующего файла JSON:</span><span class="sxs-lookup"><span data-stu-id="57ee8-114">For example, setting an environment variable `Logging:LogLevel:Default` to `Debug` value would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="57ee8-115">Чтобы обратиться к этим значениям из переменных среды, приложению достаточно вызвать AddEnvironmentVariables в ConfigurationBuilder при создании объекта IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="57ee8-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="57ee8-116">Учтите, что обычно переменные среды хранятся в виде обычного текста, и если компьютер или процесс с этими переменными среды будут скомпрометированы, значения переменных среды станут доступными.</span><span class="sxs-lookup"><span data-stu-id="57ee8-116">Note that environment variables are commonly stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a><span data-ttu-id="57ee8-117">Хранение секретов с помощью диспетчера секретов ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="57ee8-117">Store secrets with the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="57ee8-118">[Менеджер секретов](/aspnet/core/security/app-secrets#secret-manager) ASP.NET Core — это еще один инструмент для хранения секретов отдельно от исходного кода **при разработке**.</span><span class="sxs-lookup"><span data-stu-id="57ee8-118">The ASP.NET Core [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code **during development**.</span></span> <span data-ttu-id="57ee8-119">Для работы с диспетчером секретов установите пакет **Microsoft.Extensions.Configuration.SecretManager** в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="57ee8-119">To use the Secret Manager tool, install the package **Microsoft.Extensions.Configuration.SecretManager** in your project file.</span></span> <span data-ttu-id="57ee8-120">Установив и восстановив эту зависимость, можно указать значение секретов в командной строке с помощью команды `dotnet user-secrets`.</span><span class="sxs-lookup"><span data-stu-id="57ee8-120">Once that dependency is present and has been restored, the `dotnet user-secrets` command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="57ee8-121">Секреты будут храниться в файле JSON в каталоге профилей пользователей (в зависимости от ОС), отдельно от исходного кода.</span><span class="sxs-lookup"><span data-stu-id="57ee8-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="57ee8-122">Секреты, заданные диспетчером секретов, упорядочиваются свойством `UserSecretsId` в проекте, использующем эти секреты.</span><span class="sxs-lookup"><span data-stu-id="57ee8-122">Secrets set by the Secret Manager tool are organized by the `UserSecretsId` property of the project that's using the secrets.</span></span> <span data-ttu-id="57ee8-123">Поэтому обязательно задайте свойство UserSecretsId в файле проекта, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="57ee8-123">Therefore, you must be sure to set the UserSecretsId property in your project file, as shown in the snippet below.</span></span> <span data-ttu-id="57ee8-124">Значением по умолчанию является GUID, назначенный Visual Studio, но фактическая строка не важна, если она уникальна на вашем компьютере.</span><span class="sxs-lookup"><span data-stu-id="57ee8-124">The default value is a GUID assigned by Visual Studio, but the actual string is not important as long as it's unique in your computer.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="57ee8-125">Секреты, хранящиеся в диспетчере секретов, используются в приложении путем вызова `AddUserSecrets<T>` в экземпляре ConfigurationBuilder, чтобы включить секреты приложения в его конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="57ee8-125">Using secrets stored with Secret Manager in an application is accomplished by calling `AddUserSecrets<T>` on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="57ee8-126">Общий параметр T должен обозначать тип в сборке, к которой применяется UserSecretId.</span><span class="sxs-lookup"><span data-stu-id="57ee8-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="57ee8-127">Как правило, можно использовать `AddUserSecrets<Startup>`.</span><span class="sxs-lookup"><span data-stu-id="57ee8-127">Usually using `AddUserSecrets<Startup>` is fine.</span></span>

<span data-ttu-id="57ee8-128">`AddUserSecrets<Startup>()` относится к параметрам по умолчанию для среды разработки, если в `CreateDefaultBuilder`Program.cs*используется метод*.</span><span class="sxs-lookup"><span data-stu-id="57ee8-128">The `AddUserSecrets<Startup>()` is included in the default options for the Development environment when using the `CreateDefaultBuilder` method in *Program.cs*.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="57ee8-129">[Назад](authorization-net-microservices-web-applications.md)
>[Вперед](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="57ee8-129">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>
