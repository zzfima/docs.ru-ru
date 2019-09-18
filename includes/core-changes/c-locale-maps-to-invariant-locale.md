---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929990"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="9df55-101">Языковой стандарт "C" сопоставляется с инвариантным языковым стандартом</span><span class="sxs-lookup"><span data-stu-id="9df55-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="9df55-102">.NET Core 2.2 и более ранних версий зависит от поведения ICU по умолчанию, которое сопоставляет языковой стандарт "C" с языковым стандартом en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="9df55-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="9df55-103">Языковой стандарт en_US_POSIX имеет нежелательное поведение сортировки, так как не поддерживает сравнение строк без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="9df55-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="9df55-104">Так как некоторые дистрибутивы Linux устанавливают языковой стандарт "C" в качестве используемого по умолчанию, пользователи сталкивались с непредвиденным поведением.</span><span class="sxs-lookup"><span data-stu-id="9df55-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span> 

#### <a name="details"></a><span data-ttu-id="9df55-105">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9df55-105">Details</span></span>

<span data-ttu-id="9df55-106">Начиная с .NET Core 3.0 сопоставление языкового стандарта "C" изменилось на использование инвариантного (Invariant) языкового стандарта вместо en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="9df55-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="9df55-107">Для обеспечения согласованности в Windows также применяется сопоставление языкового стандарта "C" с инвариантным.</span><span class="sxs-lookup"><span data-stu-id="9df55-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="9df55-108">Сопоставление "C" с языком и региональными параметрами en_US_POSIX вызывало путаницу у клиентов, так как en_US_POSIX не поддерживает операции сортировки и поиска строк без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="9df55-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="9df55-109">Так как в некоторых дистрибутивах Linux языковой стандарт "C" используется по умолчанию, клиенты столкнулись с нежелательным поведением в этих операционных системах.</span><span class="sxs-lookup"><span data-stu-id="9df55-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="9df55-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="9df55-110">Version introduced</span></span>

<span data-ttu-id="9df55-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="9df55-111">.NET Core 3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="9df55-112">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="9df55-112">Recommended action</span></span>

<span data-ttu-id="9df55-113">Ничего конкретного, кроме сведений об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="9df55-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="9df55-114">Это изменение затрагивает только приложения, использующее сопоставление языкового параметра "C".</span><span class="sxs-lookup"><span data-stu-id="9df55-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="9df55-115">Категория</span><span class="sxs-lookup"><span data-stu-id="9df55-115">Category</span></span>

<span data-ttu-id="9df55-116">Глобализация</span><span class="sxs-lookup"><span data-stu-id="9df55-116">Globalization</span></span> 

### <a name="affected-apis"></a><span data-ttu-id="9df55-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9df55-117">Affected APIs</span></span>

<span data-ttu-id="9df55-118">Это изменение затрагивает все API параметров сортировки и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="9df55-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
