---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803261"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="0e57e-101">Согласие на прерывание для возврата от генерируемого в версии 4.5 кода SQL к более простому коду, генерируемому в версии 4.0</span><span class="sxs-lookup"><span data-stu-id="0e57e-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0e57e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0e57e-102">Details</span></span>|<span data-ttu-id="0e57e-103">Запросы, создающие операторы JOIN и содержащие вызов к операции ограничения без предварительного использования OrderBy, теперь создают более простой код SQL.</span><span class="sxs-lookup"><span data-stu-id="0e57e-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="0e57e-104">После обновления до .NET Framework 4.5 эти запросы создают более сложный код SQL, чем предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="0e57e-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="0e57e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0e57e-105">Suggestion</span></span>|<span data-ttu-id="0e57e-106">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e57e-106">This feature is disabled by default.</span></span> <span data-ttu-id="0e57e-107">Если Entity Framework создает лишние операторы JOIN, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения (app.config):</span><span class="sxs-lookup"><span data-stu-id="0e57e-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="0e57e-108">Область</span><span class="sxs-lookup"><span data-stu-id="0e57e-108">Scope</span></span>|<span data-ttu-id="0e57e-109">Прозрачно</span><span class="sxs-lookup"><span data-stu-id="0e57e-109">Transparent</span></span>|
|<span data-ttu-id="0e57e-110">Version</span><span class="sxs-lookup"><span data-stu-id="0e57e-110">Version</span></span>|<span data-ttu-id="0e57e-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="0e57e-111">4.5.2</span></span>|
|<span data-ttu-id="0e57e-112">Type</span><span class="sxs-lookup"><span data-stu-id="0e57e-112">Type</span></span>|<span data-ttu-id="0e57e-113">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="0e57e-113">Runtime</span></span>|
