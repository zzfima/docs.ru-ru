---
title: Устранение рисков. Нормализация путей
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 1e7b540975b84320d099ca004df5b6a87aa60f6a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457883"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="1a80e-102">Устранение рисков. Нормализация путей</span><span class="sxs-lookup"><span data-stu-id="1a80e-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="1a80e-103">Начиная с приложений, ориентированных на .NET Framework 4.6.2, нормализация путей в .NET Framework изменилась.</span><span class="sxs-lookup"><span data-stu-id="1a80e-103">Starting with apps the target  the .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="1a80e-104">Что такое нормализация путей?</span><span class="sxs-lookup"><span data-stu-id="1a80e-104">What is path normalization?</span></span>  
 <span data-ttu-id="1a80e-105">Нормализация пути подразумевает изменение строки, которая идентифицирует путь или файл, чтобы он соответствовал допустимому пути в целевой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="1a80e-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="1a80e-106">Нормализация обычно включает в себя:</span><span class="sxs-lookup"><span data-stu-id="1a80e-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="1a80e-107">канонизацию разделителей компонентов и каталогов;</span><span class="sxs-lookup"><span data-stu-id="1a80e-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="1a80e-108">применение текущего каталога к относительному пути;</span><span class="sxs-lookup"><span data-stu-id="1a80e-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="1a80e-109">оценку относительного каталога (`.`) или родительского каталога (`..`) в пути;</span><span class="sxs-lookup"><span data-stu-id="1a80e-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="1a80e-110">обрезку указанных символов.</span><span class="sxs-lookup"><span data-stu-id="1a80e-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="1a80e-111">Изменения</span><span class="sxs-lookup"><span data-stu-id="1a80e-111">The changes</span></span>  
 <span data-ttu-id="1a80e-112">Начиная с приложений, ориентированных на .NET Framework 4.6.2, нормализация путей изменилась следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1a80e-112">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="1a80e-113">Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1a80e-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="1a80e-114">Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).</span><span class="sxs-lookup"><span data-stu-id="1a80e-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="1a80e-115">Поддержка синтаксиса пути устройства в режиме полного доверия, включая `\\.\` и (для API-интерфейсов файлового ввода-вывода в mscorlib.dll) `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="1a80e-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="1a80e-116">Среда выполнения не проверяет пути с синтаксисом устройства.</span><span class="sxs-lookup"><span data-stu-id="1a80e-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="1a80e-117">Поддерживается использование синтаксиса устройства для доступа к альтернативным потокам данных.</span><span class="sxs-lookup"><span data-stu-id="1a80e-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="1a80e-118">Последствия</span><span class="sxs-lookup"><span data-stu-id="1a80e-118">Impact</span></span>  

<span data-ttu-id="1a80e-119">Для приложений, предназначенных для .NET Framework 4.6.2 или более поздней версии, эти изменения включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a80e-119">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="1a80e-120">Они должны улучшить производительность, позволяя методам получать доступ к ранее недоступным путям.</span><span class="sxs-lookup"><span data-stu-id="1a80e-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="1a80e-121">Это изменение не влияет на приложения, предназначенные для .NET Framework 4.6.1 и более ранних версий, но работающие на платформе .NET Framework 4.6.2 или более новой версии.</span><span class="sxs-lookup"><span data-stu-id="1a80e-121">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="1a80e-122">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="1a80e-122">Mitigation</span></span>  
 <span data-ttu-id="1a80e-123">В приложениях, предназначенных для .NET Framework 4.6.2 или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="1a80e-123">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
<span data-ttu-id="1a80e-124">В приложениях, предназначенных для .NET Framework 4.6.1 или более ранней версии, но работающих на платформе .NET Framework 4.6.2 или более поздней версии, можно включить изменения в нормализацию пути, добавив следующую строку в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="1a80e-124">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a80e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1a80e-125">See also</span></span>

- [<span data-ttu-id="1a80e-126">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="1a80e-126">Application compatibility</span></span>](application-compatibility.md)
