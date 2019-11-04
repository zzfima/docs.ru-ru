---
title: Практическое руководство. Отключение функции пропуска строгих имен
ms.date: 08/20/2019
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
ms.openlocfilehash: a4c4ae7ea61a659d3bede532da3c1bdaea448873
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141103"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a><span data-ttu-id="d918a-102">Практическое руководство. Отключение функции пропуска строгих имен</span><span class="sxs-lookup"><span data-stu-id="d918a-102">How to: Disable the strong-name bypass feature</span></span>
<span data-ttu-id="d918a-103">Начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1), подписи строгого имени не проходили проверку при загрузке сборки в объект <xref:System.AppDomain> с полным доверием, например в `MyComputer` по умолчанию для зоны <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="d918a-103">Starting with the .NET Framework version 3.5 Service Pack 1 (SP1), strong-name signatures are not validated when an assembly is loaded into a full-trust <xref:System.AppDomain> object, such as the default <xref:System.AppDomain> for the `MyComputer` zone.</span></span> <span data-ttu-id="d918a-104">Это называется возможностью обхода строгих имен.</span><span class="sxs-lookup"><span data-stu-id="d918a-104">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="d918a-105">В среде с полным доверием всегда успешно обрабатываются запросы <xref:System.Security.Permissions.StrongNameIdentityPermission> для подписанных сборок с полным доверием независимо от их подписи.</span><span class="sxs-lookup"><span data-stu-id="d918a-105">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies regardless of their signature.</span></span> <span data-ttu-id="d918a-106">Единственное исключение связано с тем, что сборка должна иметь полное доверие, потому что полное доверие имеет ее зона.</span><span class="sxs-lookup"><span data-stu-id="d918a-106">The only restriction is that the assembly must be fully trusted because its zone is fully trusted.</span></span> <span data-ttu-id="d918a-107">Так как в этом случае наличие строгого имени не является решающим фактором, смысла в проверке подписи нет.</span><span class="sxs-lookup"><span data-stu-id="d918a-107">Because the strong name is not a determining factor under these conditions, there is no reason for it to be validated.</span></span> <span data-ttu-id="d918a-108">Пропуск проверки подписей строгого имени позволяет значительно повысить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="d918a-108">Bypassing the validation of strong-name signatures provides significant performance improvements.</span></span>  
  
 <span data-ttu-id="d918a-109">Функция пропуска применяется ко всем сборкам с полным доверием, если у них нет отложенных подписей и они загружены в любой домен <xref:System.AppDomain> с полным доверием из каталога, заданным свойством <xref:System.AppDomainSetup.ApplicationBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="d918a-109">The bypass feature applies to any full-trust assembly that is not delay-signed and that is loaded into any full-trust <xref:System.AppDomain> from the directory specified by its <xref:System.AppDomainSetup.ApplicationBase%2A> property.</span></span>  
  
 <span data-ttu-id="d918a-110">Можно отключить пропуск для всех приложений на компьютере, если изменить значение параметра реестра.</span><span class="sxs-lookup"><span data-stu-id="d918a-110">You can override the bypass feature for all applications on a computer by setting a registry key value.</span></span> <span data-ttu-id="d918a-111">Для отключения пропуска для отдельного приложения необходимо внести соответствующие изменения в файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d918a-111">You can override the setting for a single application by using an application configuration file.</span></span> <span data-ttu-id="d918a-112">Если функция пропуска строгих имен отключена в реестре, ее невозможно включить для отдельного приложения.</span><span class="sxs-lookup"><span data-stu-id="d918a-112">You cannot reinstate the bypass feature for a single application if it has been disabled by the registry key.</span></span>  
  
 <span data-ttu-id="d918a-113">При отключении функции пропуска строгие имена проверяются только на правильность; наличие разрешения <xref:System.Security.Permissions.StrongNameIdentityPermission> не проверяется.</span><span class="sxs-lookup"><span data-stu-id="d918a-113">When you override the bypass feature, the strong name is validated only for correctness; it is not checked for a <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span></span> <span data-ttu-id="d918a-114">Если требуется подтвердить то или иное строгое имя, такую проверку необходимо выполнять отдельно.</span><span class="sxs-lookup"><span data-stu-id="d918a-114">If you want to confirm a specific strong name, you have to perform that check separately.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d918a-115">Возможность принудительного проведения проверки строгого имени зависит от значения параметра реестра, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d918a-115">The ability to force strong-name validation depends on a registry key, as described in the following procedure.</span></span> <span data-ttu-id="d918a-116">Если приложение выполняется от имени учетной записи, для которой в списке управления доступом не выделено разрешение на доступ к этому параметру реестра, проведение проверки невозможно.</span><span class="sxs-lookup"><span data-stu-id="d918a-116">If an application is running under an account that does not have access control list (ACL) permission to access that registry key, the setting is ineffective.</span></span> <span data-ttu-id="d918a-117">Необходимо настроить права ACL для данного раздела так, чтобы к нему могла получить доступ любая сборка.</span><span class="sxs-lookup"><span data-stu-id="d918a-117">You must ensure that ACL rights are configured for this key so that it can be read for all assemblies.</span></span>  
  
## <a name="disable-the-strong-name-bypass-feature-for-all-applications"></a><span data-ttu-id="d918a-118">Отключение функции обхода строгих имен для всех приложений</span><span class="sxs-lookup"><span data-stu-id="d918a-118">Disable the strong-name bypass feature for all applications</span></span>  
  
- <span data-ttu-id="d918a-119">На 32-разрядных компьютерах в разделе HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework системного реестра создайте запись DWORD со значением 0 и именем `AllowStrongNameBypass`.</span><span class="sxs-lookup"><span data-stu-id="d918a-119">On 32-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
- <span data-ttu-id="d918a-120">На 64-разрядных компьютерах в разделах системного реестра HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework и HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework создать запись типа DWORD со значением 0 с именем `AllowStrongNameBypass`.</span><span class="sxs-lookup"><span data-stu-id="d918a-120">On 64-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework and HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework keys.</span></span>  
  
## <a name="disable-the-strong-name-bypass-feature-for-a-single-application"></a><span data-ttu-id="d918a-121">Отключение функции обхода строгих имен для отдельного приложения</span><span class="sxs-lookup"><span data-stu-id="d918a-121">Disable the strong-name bypass feature for a single application</span></span>  
  
1. <span data-ttu-id="d918a-122">Откройте или создайте файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d918a-122">Open or create the application configuration file.</span></span>  
  
    <span data-ttu-id="d918a-123">Дополнительные сведения об этом файле см. в разделе "Файлы конфигурации приложений" документа [Настройка приложений](../../framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="d918a-123">For more information about this file, see the Application Configuration Files section in [Configure apps](../../framework/configure-apps/index.md).</span></span>  
  
2. <span data-ttu-id="d918a-124">Добавьте следующую запись:</span><span class="sxs-lookup"><span data-stu-id="d918a-124">Add the following entry:</span></span>  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 <span data-ttu-id="d918a-125">Функцию пропуска строгих имен для приложения можно снова включить, удалив соответствующий элемент из файла конфигурации или установив для атрибута значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d918a-125">You can restore the bypass feature for the application by removing the configuration file setting or by setting the attribute to `true`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d918a-126">Функцию проверки строгих имен можно включать и отключать на уровне приложения, если пропуск строгих имен включен на уровне компьютера.</span><span class="sxs-lookup"><span data-stu-id="d918a-126">You can turn strong-name validation on and off for an application only if the bypass feature is enabled for the computer.</span></span> <span data-ttu-id="d918a-127">Если функция пропуска на уровне компьютера отключена, строгие имена будут проверяться для всех приложений и пропустить проверку для отдельного приложения будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="d918a-127">If the bypass feature has been turned off for the computer, strong names are validated for all applications and you cannot bypass validation for a single application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d918a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d918a-128">See also</span></span>

- [<span data-ttu-id="d918a-129">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="d918a-129">Sn.exe (Strong Name Tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="d918a-130">Элемент \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="d918a-130">\<bypassTrustedAppStrongNames> element</span></span>](../../framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [<span data-ttu-id="d918a-131">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="d918a-131">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
