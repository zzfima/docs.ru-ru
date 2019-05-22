---
ms.openlocfilehash: 9c72bc686e014a0bffdf272e3813358d1b29cc66
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "65199396"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="17b6b-101">.NET COM успешно маршалирует параметры ByRef SafeArray в события</span><span class="sxs-lookup"><span data-stu-id="17b6b-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="17b6b-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="17b6b-102">Details</span></span>|<span data-ttu-id="17b6b-103">В .NET Framework 4.7.2 и более ранних версиях параметр ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) события COM не позволял выполнить маршалинг обратно в машинный код.</span><span class="sxs-lookup"><span data-stu-id="17b6b-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="17b6b-104">Благодаря этому изменению [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) теперь успешно маршалируется.</span><span class="sxs-lookup"><span data-stu-id="17b6b-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshaled successfully.</span></span><ul><li><span data-ttu-id="17b6b-105">[x] Режим совместимости</span><span class="sxs-lookup"><span data-stu-id="17b6b-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="17b6b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="17b6b-106">Suggestion</span></span>|<span data-ttu-id="17b6b-107">Если правильный маршалинг параметров ByRef SafeArray в события COM нарушает выполнение, этот код можно отключить, добавив следующий параметр конфигурации в файл конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="17b6b-107">If properly marshaling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="17b6b-108">Область</span><span class="sxs-lookup"><span data-stu-id="17b6b-108">Scope</span></span>|<span data-ttu-id="17b6b-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="17b6b-109">Minor</span></span>|
|<span data-ttu-id="17b6b-110">Версия</span><span class="sxs-lookup"><span data-stu-id="17b6b-110">Version</span></span>|<span data-ttu-id="17b6b-111">4.8</span><span class="sxs-lookup"><span data-stu-id="17b6b-111">4.8</span></span>|
|<span data-ttu-id="17b6b-112">Тип</span><span class="sxs-lookup"><span data-stu-id="17b6b-112">Type</span></span>|<span data-ttu-id="17b6b-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="17b6b-113">Runtime</span></span>|
