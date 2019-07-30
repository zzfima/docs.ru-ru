---
ms.openlocfilehash: 9c54572b8dcedaa103db8503cfc1155b4698c3ed
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803456"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="aec05-101">Контрольные суммы рабочего процесса XAML для символов изменены с SHA1 на SHA256</span><span class="sxs-lookup"><span data-stu-id="aec05-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="aec05-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="aec05-102">Details</span></span>|<span data-ttu-id="aec05-103">Для поддержки отладки в Visual Studio среда выполнения рабочего процесса создает контрольную сумму для файла XAML рабочего процесса, используя алгоритм хэширования.</span><span class="sxs-lookup"><span data-stu-id="aec05-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="aec05-104">В .NET Framework 4.6.2 и более ранних версий для хэширования контрольной суммы рабочего процесса использовался алгоритм MD5, что приводило к проблемам в системах с поддержкой стандарта FIPS.</span><span class="sxs-lookup"><span data-stu-id="aec05-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="aec05-105">Начиная с .NET Framework 4.7 алгоритм по умолчанию изменен на SHA-1.</span><span class="sxs-lookup"><span data-stu-id="aec05-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="aec05-106">Начиная с .NET Framework 4.8 алгоритм по умолчанию изменен на SHA256.</span><span class="sxs-lookup"><span data-stu-id="aec05-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>|
|<span data-ttu-id="aec05-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="aec05-107">Suggestion</span></span>|<span data-ttu-id="aec05-108">Если код не может загрузить экземпляры рабочих процессов или найти подходящие символы из-за ошибки контрольной суммы, попробуйте установить для параметра <code>AppContext</code> &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; значение true. В коде:</span><span class="sxs-lookup"><span data-stu-id="aec05-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the <code>AppContext</code> switch &quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot; to true.In code:</span></span><pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols&quot;, true);&#13;&#10;</code></pre><span data-ttu-id="aec05-109">Или в конфигурации:</span><span class="sxs-lookup"><span data-stu-id="aec05-109">Or in configuration:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="aec05-110">Область</span><span class="sxs-lookup"><span data-stu-id="aec05-110">Scope</span></span>|<span data-ttu-id="aec05-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="aec05-111">Minor</span></span>|
|<span data-ttu-id="aec05-112">Версия</span><span class="sxs-lookup"><span data-stu-id="aec05-112">Version</span></span>|<span data-ttu-id="aec05-113">4.8</span><span class="sxs-lookup"><span data-stu-id="aec05-113">4.8</span></span>|
|<span data-ttu-id="aec05-114">Тип</span><span class="sxs-lookup"><span data-stu-id="aec05-114">Type</span></span>|<span data-ttu-id="aec05-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="aec05-115">Retargeting</span></span>|
