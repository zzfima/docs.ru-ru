---
title: "Устранение рисков: управление версиями продукта"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0c69eaefde812d8910ebfc329765d0571701da25
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="db5be-102">Устранение рисков: управление версиями продукта</span><span class="sxs-lookup"><span data-stu-id="db5be-102">Mitigation: Product Versioning</span></span>
<span data-ttu-id="db5be-103">В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и более поздних версиях управление версиями продукта отличается от предыдущих выпусков платформы .NET Framework (.NET Framework 4, 4.5, 4.5.1 и 4.5.2).</span><span class="sxs-lookup"><span data-stu-id="db5be-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>  
  
## <a name="product-versioning-changes"></a><span data-ttu-id="db5be-104">Изменения управления версиями продукта</span><span class="sxs-lookup"><span data-stu-id="db5be-104">Product versioning changes</span></span>  
 <span data-ttu-id="db5be-105">Ниже приведено подробное описание изменений.</span><span class="sxs-lookup"><span data-stu-id="db5be-105">The following are the detailed changes:</span></span>  
  
-   <span data-ttu-id="db5be-106">Значение записи `Version` в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` изменилось на `4.6.`*xxxxx* в .NET Framework 4.6 и ее доработанных версиях и на `4.7.`*xxxxx* в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="db5be-106">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="db5be-107">В .NET Framework 4.5, 4.5.1 и 4.5.2 использовался формат `4.5.`*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="db5be-107">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>  
  
-   <span data-ttu-id="db5be-108">Управление версиями файлов и продукта для файлов .NET Framework было изменено с более ранней схемы управления версиями `4.0.30319.x` на `4.6.X.0` для .NET Framework 4.6 и ее доработанных выпусков, а также на `4.7.X.0` для .NET Framework 4.7 и ее доработанных выпусков.</span><span class="sxs-lookup"><span data-stu-id="db5be-108">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="db5be-109">Вы можете увидеть эти новые значения в **свойствах** файла, щелкнув файл правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="db5be-109">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>  
  
-   <span data-ttu-id="db5be-110">Атрибуты <xref:System.Reflection.AssemblyFileVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute> для управляемых сборок имеют значения <xref:System.Version> в виде `4.6.X.0` на платформе .NET Framework 4.6 и в ее доработанных выпусках или `4.7.X.0` на платформе .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="db5be-110">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>  
  
-   <span data-ttu-id="db5be-111">В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 и 4.7 свойство <xref:System.Environment.Version%2A?displayProperty=fullName> возвращает исправленную строку версии `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="db5be-111">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7, the <xref:System.Environment.Version%2A?displayProperty=fullName> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="db5be-112">В .NET Framework 4, 4.5, 4.5.1 и 4.5.2 оно возвращает строки версии в формате `4.0.30319.xxxxx` (например, "4.0.30319.18010").</span><span class="sxs-lookup"><span data-stu-id="db5be-112">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="db5be-113">Обратите внимание, что создание в свойстве <xref:System.Environment.Version%2A?displayProperty=fullName> новых зависимостей от кода приложения не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="db5be-113">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=fullName> property.</span></span>  
  
### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="db5be-114">Обработка изменений управления версиями продукта</span><span class="sxs-lookup"><span data-stu-id="db5be-114">Handling the product versioning changes</span></span>  
 <span data-ttu-id="db5be-115">В общем случае приложения для обнаружения таких сведений, как версия среды выполнения .NET Framework и каталог установки, должны использовать следующие рекомендуемые методы:</span><span class="sxs-lookup"><span data-stu-id="db5be-115">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>  
  
-   <span data-ttu-id="db5be-116">Инструкции для определения версии среды выполнения .NET см. в разделе [Практическое руководство. Определение установленных версий платформы .NET Framework](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="db5be-116">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>  
  
-   <span data-ttu-id="db5be-117">Чтобы определить путь установки платформы .NET Framework, используйте значение записи `InstallPath` в ключе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.</span><span class="sxs-lookup"><span data-stu-id="db5be-117">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="db5be-118">Имя подраздела — `NET Framework Setup`, а не `.NET Framework Setup`.</span><span class="sxs-lookup"><span data-stu-id="db5be-118">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>  
  
-   <span data-ttu-id="db5be-119">Чтобы определить путь к каталогу общеязыковой среды выполнения .NET Framework, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="db5be-119">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName> method.</span></span>  
  
-   <span data-ttu-id="db5be-120">Чтобы получить версию среды CLR, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="db5be-120">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName> method.</span></span>   <span data-ttu-id="db5be-121">Для .NET Framework 4 и ее доработанных выпусков (.NET Framework 4.5, 4.5.1, 4.5.2 и [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, 4.7) возвращается строка `v4.0.30319`.</span><span class="sxs-lookup"><span data-stu-id="db5be-121">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5be-122">См. также</span><span class="sxs-lookup"><span data-stu-id="db5be-122">See Also</span></span>  
 [<span data-ttu-id="db5be-123">Изменения среды выполнения</span><span class="sxs-lookup"><span data-stu-id="db5be-123">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 

