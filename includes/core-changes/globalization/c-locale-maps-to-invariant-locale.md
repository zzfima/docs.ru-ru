---
ms.openlocfilehash: 9e9e443be9ea51d214e95c676fc28f0d8790af8b
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117184"
---
### <a name="c-locale-maps-to-the-invariant-locale"></a><span data-ttu-id="ec7bc-101">Языковой стандарт "C" сопоставляется с инвариантным языковым стандартом</span><span class="sxs-lookup"><span data-stu-id="ec7bc-101">"C" locale maps to the invariant locale</span></span>

<span data-ttu-id="ec7bc-102">.NET Core 2.2 и более ранних версий зависит от поведения ICU по умолчанию, которое сопоставляет языковой стандарт "C" с языковым стандартом en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-102">.NET Core 2.2 and earlier versions depend on the default ICU behavior, which maps the "C" locale to the en_US_POSIX locale.</span></span> <span data-ttu-id="ec7bc-103">Языковой стандарт en_US_POSIX имеет нежелательное поведение сортировки, так как не поддерживает сравнение строк без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-103">The en_US_POSIX locale has an undesirable collation behavior, because it doesn't support case-insensitive string comparisons.</span></span> <span data-ttu-id="ec7bc-104">Так как некоторые дистрибутивы Linux устанавливают языковой стандарт "C" в качестве используемого по умолчанию, пользователи сталкивались с непредвиденным поведением.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-104">Because some Linux distributions set the "C" locale as the default locale, users were experiencing unexpected behavior.</span></span> 

#### <a name="details"></a><span data-ttu-id="ec7bc-105">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ec7bc-105">Details</span></span>

<span data-ttu-id="ec7bc-106">Начиная с .NET Core 3.0 сопоставление языкового стандарта "C" изменилось на использование инвариантного (Invariant) языкового стандарта вместо en_US_POSIX.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-106">Starting with .NET Core 3.0, the "C" locale mapping has changed to use the Invariant locale instead of en_US_POSIX.</span></span> <span data-ttu-id="ec7bc-107">Для обеспечения согласованности в Windows также применяется сопоставление языкового стандарта "C" с инвариантным.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-107">The "C" locale to Invariant mapping is also applied to Windows for consistency.</span></span>

<span data-ttu-id="ec7bc-108">Сопоставление "C" с языком и региональными параметрами en_US_POSIX вызывало путаницу у клиентов, так как en_US_POSIX не поддерживает операции сортировки и поиска строк без учета регистра.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-108">Mapping "C" to en_US_POSIX culture caused customer confusion, because en_US_POSIX doesn't support case insensitive sorting/searching string operations.</span></span> <span data-ttu-id="ec7bc-109">Так как в некоторых дистрибутивах Linux языковой стандарт "C" используется по умолчанию, клиенты столкнулись с нежелательным поведением в этих операционных системах.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-109">Because the "C" locale is used as a default locale in some of the Linux distros, customers experienced this undesired behavior on these operating systems.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="ec7bc-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ec7bc-110">Version introduced</span></span>

<span data-ttu-id="ec7bc-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ec7bc-111">.NET Core 3.0</span></span>

### <a name="recommended-action"></a><span data-ttu-id="ec7bc-112">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="ec7bc-112">Recommended action</span></span>

<span data-ttu-id="ec7bc-113">Ничего конкретного, кроме сведений об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-113">Nothing specific more than the awareness of this change.</span></span> <span data-ttu-id="ec7bc-114">Это изменение затрагивает только приложения, использующее сопоставление языкового параметра "C".</span><span class="sxs-lookup"><span data-stu-id="ec7bc-114">This change affects only applications that use the "C" locale mapping.</span></span>

### <a name="category"></a><span data-ttu-id="ec7bc-115">Категория</span><span class="sxs-lookup"><span data-stu-id="ec7bc-115">Category</span></span>

<span data-ttu-id="ec7bc-116">Глобализация</span><span class="sxs-lookup"><span data-stu-id="ec7bc-116">Globalization</span></span> 

### <a name="affected-apis"></a><span data-ttu-id="ec7bc-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ec7bc-117">Affected APIs</span></span>

<span data-ttu-id="ec7bc-118">Это изменение затрагивает все API параметров сортировки и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="ec7bc-118">All collation and culture APIs are affected by this change.</span></span>

<!--

-->
