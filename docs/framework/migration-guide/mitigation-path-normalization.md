---
title: "Устранение рисков. Нормализация путей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e30099e315f88bd051dca2e1f6c83d1bccc49569
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="1f37c-102">Устранение рисков. Нормализация путей</span><span class="sxs-lookup"><span data-stu-id="1f37c-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="1f37c-103">Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей в .NET Framework изменилась.</span><span class="sxs-lookup"><span data-stu-id="1f37c-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="1f37c-104">Что такое нормализация путей?</span><span class="sxs-lookup"><span data-stu-id="1f37c-104">What is path normalization?</span></span>  
 <span data-ttu-id="1f37c-105">Нормализация пути подразумевает изменение строки, которая идентифицирует путь или файл, чтобы он соответствовал допустимому пути в целевой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="1f37c-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="1f37c-106">Нормализация обычно включает в себя:</span><span class="sxs-lookup"><span data-stu-id="1f37c-106">Normalization typically involves:</span></span>  
  
-   <span data-ttu-id="1f37c-107">канонизацию разделителей компонентов и каталогов;</span><span class="sxs-lookup"><span data-stu-id="1f37c-107">Canonicalizing component and directory separators.</span></span>  
  
-   <span data-ttu-id="1f37c-108">применение текущего каталога к относительному пути;</span><span class="sxs-lookup"><span data-stu-id="1f37c-108">Applying the current directory to a relative path.</span></span>  
  
-   <span data-ttu-id="1f37c-109">оценку относительного каталога (`.`) или родительского каталога (`..`) в пути;</span><span class="sxs-lookup"><span data-stu-id="1f37c-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
-   <span data-ttu-id="1f37c-110">обрезку указанных символов.</span><span class="sxs-lookup"><span data-stu-id="1f37c-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="1f37c-111">Изменения</span><span class="sxs-lookup"><span data-stu-id="1f37c-111">The changes</span></span>  
 <span data-ttu-id="1f37c-112">Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей изменилась в следующих направлениях.</span><span class="sxs-lookup"><span data-stu-id="1f37c-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="1f37c-113">Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1f37c-113">The runtime defers to the operating system's [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) function to normalize paths.</span></span>  
  
-   <span data-ttu-id="1f37c-114">Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).</span><span class="sxs-lookup"><span data-stu-id="1f37c-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
-   <span data-ttu-id="1f37c-115">Поддержка синтаксиса пути устройства в режиме полного доверия, включая `\\.\` и (для API-интерфейсов файлового ввода-вывода в mscorlib.dll) `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="1f37c-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
-   <span data-ttu-id="1f37c-116">Среда выполнения не проверяет пути с синтаксисом устройства.</span><span class="sxs-lookup"><span data-stu-id="1f37c-116">The runtime does not validate device syntax paths.</span></span>  
  
-   <span data-ttu-id="1f37c-117">Поддерживается использование синтаксиса устройства для доступа к альтернативным потокам данных.</span><span class="sxs-lookup"><span data-stu-id="1f37c-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1f37c-118">Последствия</span><span class="sxs-lookup"><span data-stu-id="1f37c-118">Impact</span></span>  
 <span data-ttu-id="1f37c-119">Для приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, эти изменения включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1f37c-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="1f37c-120">Они должны улучшить производительность, позволяя методам получать доступ к ранее недоступным путям.</span><span class="sxs-lookup"><span data-stu-id="1f37c-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="1f37c-121">Это изменение не влияет на приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, но работающие на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более новой версии.</span><span class="sxs-lookup"><span data-stu-id="1f37c-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1f37c-122">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="1f37c-122">Mitigation</span></span>  
 <span data-ttu-id="1f37c-123">В приложениях, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="1f37c-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="1f37c-124">В приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] или более ранней версии, но работающих на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, можно включить изменения в нормализацию пути, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="1f37c-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f37c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1f37c-125">See Also</span></span>  
 [<span data-ttu-id="1f37c-126">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="1f37c-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

