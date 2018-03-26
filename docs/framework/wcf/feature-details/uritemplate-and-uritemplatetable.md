---
title: UriTemplate и UriTemplateTable
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cbbe03f-4a9e-4d44-9e02-c5773239cf52
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac77fe2c83828d2cc9473417d2b29b2d2e540923
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="uritemplate-and-uritemplatetable"></a><span data-ttu-id="c686a-102">UriTemplate и UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c686a-102">UriTemplate and UriTemplateTable</span></span>
<span data-ttu-id="c686a-103">Веб-разработчикам необходима возможность описания формы и структуры универсальных кодов ресурса (URI), на которые отвечают их службы.</span><span class="sxs-lookup"><span data-stu-id="c686a-103">Web developers require the ability to describe the shape and layout of the URIs that their services respond to.</span></span> <span data-ttu-id="c686a-104">В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] появились два новых класса, позволяющие разработчикам контролировать свои URI.</span><span class="sxs-lookup"><span data-stu-id="c686a-104">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] added two new classes to give developers control over their URIs.</span></span> <span data-ttu-id="c686a-105">Классы <xref:System.UriTemplate> и <xref:System.UriTemplateTable> формируют основу модуля отправки данных на основе URI, который используется в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c686a-105"><xref:System.UriTemplate> and <xref:System.UriTemplateTable> form the basis of the URI-based dispatch engine in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="c686a-106">Эти классы могут также использоваться сами по себе, позволяя разработчиками воспользоваться преимуществами шаблонов и механизма сопоставления универсального кода ресурса (URI) без реализации службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c686a-106">These classes can also be used on their own, allowing developers to take advantage of templates and the URI mapping mechanism without implementing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="templates"></a><span data-ttu-id="c686a-107">Шаблоны</span><span class="sxs-lookup"><span data-stu-id="c686a-107">Templates</span></span>  
 <span data-ttu-id="c686a-108">Шаблон - это способ описания набора относительных универсальных кодов ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-108">A template is a way to describe a set of relative URIs.</span></span> <span data-ttu-id="c686a-109">Набор шаблонов универсальных кодов ресурсов (URI), приведенный в следующей таблице, показывает, как может быть определена система, извлекающая различные виды информации о погоде.</span><span class="sxs-lookup"><span data-stu-id="c686a-109">The set of URI templates in the following table shows how a system that retrieves various types of weather information might be defined.</span></span>  
  
|<span data-ttu-id="c686a-110">Данные</span><span class="sxs-lookup"><span data-stu-id="c686a-110">Data</span></span>|<span data-ttu-id="c686a-111">Шаблон</span><span class="sxs-lookup"><span data-stu-id="c686a-111">Template</span></span>|  
|----------|--------------|  
|<span data-ttu-id="c686a-112">Прогноз для страны</span><span class="sxs-lookup"><span data-stu-id="c686a-112">National Forecast</span></span>|<span data-ttu-id="c686a-113">weather/national</span><span class="sxs-lookup"><span data-stu-id="c686a-113">weather/national</span></span>|  
|<span data-ttu-id="c686a-114">Прогноз для штата</span><span class="sxs-lookup"><span data-stu-id="c686a-114">State Forecast</span></span>|<span data-ttu-id="c686a-115">weather/{state}</span><span class="sxs-lookup"><span data-stu-id="c686a-115">weather/{state}</span></span>|  
|<span data-ttu-id="c686a-116">Прогноз для города</span><span class="sxs-lookup"><span data-stu-id="c686a-116">City Forecast</span></span>|<span data-ttu-id="c686a-117">weather/{state}/{city}</span><span class="sxs-lookup"><span data-stu-id="c686a-117">weather/{state}/{city}</span></span>|  
|<span data-ttu-id="c686a-118">Прогноз для рода занятий</span><span class="sxs-lookup"><span data-stu-id="c686a-118">Activity Forecast</span></span>|<span data-ttu-id="c686a-119">weather/{state}/{city}/{activity}</span><span class="sxs-lookup"><span data-stu-id="c686a-119">weather/{state}/{city}/{activity}</span></span>|  
  
 <span data-ttu-id="c686a-120">В этой таблице описывает набор, структурно аналогичный универсальным кодам ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-120">This table describes a set of structurally similar URIs.</span></span> <span data-ttu-id="c686a-121">Каждая запись является шаблоном универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-121">Each entry is a URI template.</span></span> <span data-ttu-id="c686a-122">Сегменты в фигурных скобках описывают переменные.</span><span class="sxs-lookup"><span data-stu-id="c686a-122">The segments in curly braces describe variables.</span></span> <span data-ttu-id="c686a-123">Сегменты без фигурных скобок описывают строки литералов.</span><span class="sxs-lookup"><span data-stu-id="c686a-123">The segments not in curly braces describe literal strings.</span></span> <span data-ttu-id="c686a-124">Классы шаблонов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяют разработчику сопоставить входящий универсальный код ресурса (URI) (например, "/weather/wa/seattle/cycling") с описывающим его шаблоном ("/weather/{state}/{city}/{activity}").</span><span class="sxs-lookup"><span data-stu-id="c686a-124">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] template classes allow a developer to take an incoming URI, for example, "/weather/wa/seattle/cycling", and match it to a template that describes it, "/weather/{state}/{city}/{activity}".</span></span>  
  
## <a name="uritemplate"></a><span data-ttu-id="c686a-125">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c686a-125">UriTemplate</span></span>  
 <span data-ttu-id="c686a-126">Класс <xref:System.UriTemplate> является классом, инкапсулирующим шаблон универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-126"><xref:System.UriTemplate> is a class that encapsulates a URI template.</span></span> <span data-ttu-id="c686a-127">Конструктор принимает строковый параметр, задающий шаблон.</span><span class="sxs-lookup"><span data-stu-id="c686a-127">The constructor takes a string parameter that defines the template.</span></span> <span data-ttu-id="c686a-128">Эта строка содержит шаблон в формате, приведенном в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="c686a-128">This string contains the template in the format described in the next section.</span></span> <span data-ttu-id="c686a-129">Класс <xref:System.UriTemplate> предоставляет методы, позволяющие сопоставлять входящий URI с шаблоном, создавать URI из шаблона, получать коллекцию имен переменных в шаблоне, определять, эквивалентны ли два шаблона, и возвращать строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-129">The <xref:System.UriTemplate> class provides methods that allow you match an incoming URI to a template, generate a URI from a template, retrieve a collection of variable names used in the template, determine whether two templates are equivalent, and return the template's string.</span></span>  
  
 <span data-ttu-id="c686a-130">Метод <xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> принимает базовый адрес и потенциальный универсальный код ресурса (URI), после чего пытается сопоставить универсальный код ресурса (URI) с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="c686a-130"><xref:System.UriTemplate.Match%28System.Uri%2CSystem.Uri%29> takes a base address and a candidate URI and attempts to match the URI to the template.</span></span> <span data-ttu-id="c686a-131">Если сопоставление завершается успешно, возвращается экземпляр <xref:System.UriTemplateMatch>.</span><span class="sxs-lookup"><span data-stu-id="c686a-131">If the match is successful, a <xref:System.UriTemplateMatch> instance is returned.</span></span> <span data-ttu-id="c686a-132">Объект <xref:System.UriTemplateMatch> содержит базовый универсальный код ресурса (URI), потенциальный URI, коллекцию имя/значение параметров запроса, массив сегментов относительного пути, коллекцию имя/значение сопоставленных переменных, экземпляр <xref:System.UriTemplate>, использованный для сопоставления, строку, содержащую несопоставленную часть потенциального URI (используется, если шаблон содержит подстановочный знак) и объект, связанный с этим шаблоном.</span><span class="sxs-lookup"><span data-stu-id="c686a-132">The <xref:System.UriTemplateMatch> object contains a base URI, the candidate URI, a name/value collection of the query parameters, an array of the relative path segments, a name/value collection of variables that were matched, the <xref:System.UriTemplate> instance used to perform the match, a string that contains any unmatched portion of the candidate URI (used when the template has a wildcard), and an object that is associated with the template.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c686a-133">При сопоставлении потенциального универсального кода ресурса (URI) класс <xref:System.UriTemplate> не учитывает схему и номер порта.</span><span class="sxs-lookup"><span data-stu-id="c686a-133">The <xref:System.UriTemplate> class ignores the scheme and port number when matching a candidate URI to a template.</span></span>  
  
 <span data-ttu-id="c686a-134">Есть два метода, позволяющие создавать URI из шаблона, - <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> и <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="c686a-134">There are two methods that allow you to generate a URI from a template, <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> and <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29>.</span></span> <span data-ttu-id="c686a-135">Метод <xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> принимает базовый адрес и коллекцию параметров вида «имя–значение».</span><span class="sxs-lookup"><span data-stu-id="c686a-135"><xref:System.UriTemplate.BindByName%28System.Uri%2CSystem.Collections.Specialized.NameValueCollection%29> takes a base address and a name/value collection of parameters.</span></span> <span data-ttu-id="c686a-136">Эти параметры подставляются вместо переменных при использовании шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-136">These parameters are substituted for variables when the template is bound.</span></span> <span data-ttu-id="c686a-137">Метод <xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> принимает пары «имя–значение» и подставляет их в порядке слева направо.</span><span class="sxs-lookup"><span data-stu-id="c686a-137"><xref:System.UriTemplate.BindByPosition%28System.Uri%2CSystem.String%5B%5D%29> takes the name/value pairs and substitutes them left to right.</span></span>  
  
 <span data-ttu-id="c686a-138">Метод <xref:System.UriTemplate.ToString> возвращает строку шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-138"><xref:System.UriTemplate.ToString> returns the template string.</span></span>  
  
 <span data-ttu-id="c686a-139">Свойство <xref:System.UriTemplate.PathSegmentVariableNames%2A> содержит коллекцию имен переменных, используемых в сегментах пути в строке шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-139">The <xref:System.UriTemplate.PathSegmentVariableNames%2A> property contains a collection of the names of the variables used within path segments in the template string.</span></span>  
  
 <span data-ttu-id="c686a-140">Метод <xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> принимает <xref:System.UriTemplate> в качестве параметра и возвращает логическое значение, указывающее, являются ли два шаблона эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="c686a-140"><xref:System.UriTemplate.IsEquivalentTo%28System.UriTemplate%29> takes a <xref:System.UriTemplate> as a parameter and returns a Boolean value that specifies whether the two templates are equivalent.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c686a-141"> подраздел «Эквивалентность шаблонов» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c686a-141"> the Template Equivalence section later in this topic.</span></span>  
  
 <span data-ttu-id="c686a-142">Класс <xref:System.UriTemplate> предназначен для работы с любой схемой URI, соблюдающей грамматику URI HTTP.</span><span class="sxs-lookup"><span data-stu-id="c686a-142"><xref:System.UriTemplate> is designed to work with any URI scheme that conforms to the HTTP URI grammar.</span></span> <span data-ttu-id="c686a-143">Ниже приведены примеры поддерживаемых схем URI.</span><span class="sxs-lookup"><span data-stu-id="c686a-143">The following are examples of supported URI schemes.</span></span>  
  
-   <span data-ttu-id="c686a-144">http://</span><span class="sxs-lookup"><span data-stu-id="c686a-144">http://</span></span>  
  
-   <span data-ttu-id="c686a-145">https://</span><span class="sxs-lookup"><span data-stu-id="c686a-145">https://</span></span>  
  
-   <span data-ttu-id="c686a-146">net.tcp://</span><span class="sxs-lookup"><span data-stu-id="c686a-146">net.tcp://</span></span>  
  
-   <span data-ttu-id="c686a-147">net.pipe://</span><span class="sxs-lookup"><span data-stu-id="c686a-147">net.pipe://</span></span>  
  
-   <span data-ttu-id="c686a-148">sb://</span><span class="sxs-lookup"><span data-stu-id="c686a-148">sb://</span></span>  
  
 <span data-ttu-id="c686a-149">Схемы, подобные file:// и urn://, не соответствуют грамматике URI HTTP и при использовании с шаблонами URI приведут к непредсказуемым результатам.</span><span class="sxs-lookup"><span data-stu-id="c686a-149">Schemes like file:// and urn:// do not conform to the HTTP URI grammar and cause unpredictable results when used with URI templates.</span></span>  
  
### <a name="template-string-syntax"></a><span data-ttu-id="c686a-150">Синтаксис строки шаблона</span><span class="sxs-lookup"><span data-stu-id="c686a-150">Template String Syntax</span></span>  
 <span data-ttu-id="c686a-151">Шаблон содержит три части: путь, необязательный запрос и необязательный фрагмент.</span><span class="sxs-lookup"><span data-stu-id="c686a-151">A template has three parts: a path, an optional query, and an optional fragment.</span></span> <span data-ttu-id="c686a-152">Например, рассмотрим следующий шаблон:</span><span class="sxs-lookup"><span data-stu-id="c686a-152">For an example, see the following template:</span></span>  
  
```  
"/weather/{state}/{city}?forecast={length)#frag1  
```  
  
 <span data-ttu-id="c686a-153">Путь состоит из «/weather/{state}/{city}», запрос состоит из «?forecast={length}», и фрагмент состоит из «#frag1».</span><span class="sxs-lookup"><span data-stu-id="c686a-153">The path consists of "/weather/{state}/{city}", the query consists of "?forecast={length}, and the fragment consists of "#frag1".</span></span>  
  
 <span data-ttu-id="c686a-154">Начальные и конечные знаки косой черты в выражении пути необязательны.</span><span class="sxs-lookup"><span data-stu-id="c686a-154">Leading and trailing slashes are optional in the path expression.</span></span> <span data-ttu-id="c686a-155">Как запрос, так и фрагмент могут быть полностью опущены.</span><span class="sxs-lookup"><span data-stu-id="c686a-155">Both the query and fragment expressions can be omitted entirely.</span></span> <span data-ttu-id="c686a-156">Путь состоит из ряда сегментов, разделенных «/», каждый сегмент имеет литеральное значение, имя переменной (указанное в {фигурных скобках}) или подстановочный знак (записан как\*").</span><span class="sxs-lookup"><span data-stu-id="c686a-156">A path consists of a series of segments delimited by '/', each segment can have a literal value, a variable name (written in {curly braces}), or a wildcard (written as '\*').</span></span> <span data-ttu-id="c686a-157">В предыдущем шаблоне сегмент "\weather\" является литеральным значением, а "{state}" и "{city}" - это переменные.</span><span class="sxs-lookup"><span data-stu-id="c686a-157">In the previous template the "\weather\ segment is a literal value while "{state}" and "{city}" are variables.</span></span> <span data-ttu-id="c686a-158">Переменные имеют имя, содержимое их фигурных скобок и может быть заменен более поздней версии с конкретными значениями для создания *закрытого URI*.</span><span class="sxs-lookup"><span data-stu-id="c686a-158">Variables take their name from the contents of their curly braces and they can later be replaced with a concrete value to create a *closed URI*.</span></span> <span data-ttu-id="c686a-159">Подстановочный знак является необязательным, но может использоваться только в конце URI, где он логически означает «оставшуюся часть пути».</span><span class="sxs-lookup"><span data-stu-id="c686a-159">The wildcard is optional, but can only appear at the end of the URI, where it logically matches "the rest of the path".</span></span>  
  
 <span data-ttu-id="c686a-160">Выражение запроса (если оно указано) задает неупорядоченную последовательность пар «имя-значение», разделяемых знаком «&».</span><span class="sxs-lookup"><span data-stu-id="c686a-160">The query expression, if present, specifies a series of unordered name/value pairs delimited by '&'.</span></span> <span data-ttu-id="c686a-161">Элементами выражения запроса могут быть либо литеральные пары (x=2) или переменная пара (x={var}).</span><span class="sxs-lookup"><span data-stu-id="c686a-161">Elements of the query expression can either be literal pairs (x=2) or a variable pair (x={var}).</span></span> <span data-ttu-id="c686a-162">Переменное выражение может содержаться только в правой части запроса.</span><span class="sxs-lookup"><span data-stu-id="c686a-162">Only the right side of the query can have a variable expression.</span></span> <span data-ttu-id="c686a-163">Конструкции ({someName} = {someValue}) не допускаются.</span><span class="sxs-lookup"><span data-stu-id="c686a-163">({someName} = {someValue} is not allowed.</span></span> <span data-ttu-id="c686a-164">Непарные значения (?x) не допускаются.</span><span class="sxs-lookup"><span data-stu-id="c686a-164">Unpaired values (?x) are not permitted.</span></span> <span data-ttu-id="c686a-165">Нет никаких различий между пустой запрос выражения и выражения запроса, состоящий из одного лишь "?" (оба означает «любого запроса»).</span><span class="sxs-lookup"><span data-stu-id="c686a-165">There is no difference between an empty query expression and a query expression consisting of just a single '?' (both mean "any query").</span></span>  
  
 <span data-ttu-id="c686a-166">Выражение фрагмента может содержать любое литеральное значение, переменные не допускаются.</span><span class="sxs-lookup"><span data-stu-id="c686a-166">The fragment expression can consist of a literal value, no variables are allowed.</span></span>  
  
 <span data-ttu-id="c686a-167">Все имена переменных шаблона в строке шаблона должны быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="c686a-167">All template variable names within a template string must be unique.</span></span> <span data-ttu-id="c686a-168">В именах переменных шаблона регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="c686a-168">Template variable names are case-insensitive.</span></span>  
  
 <span data-ttu-id="c686a-169">Ниже приведены допустимые строки шаблона:</span><span class="sxs-lookup"><span data-stu-id="c686a-169">Examples of valid template strings:</span></span>  
  
-   <span data-ttu-id="c686a-170">""</span><span class="sxs-lookup"><span data-stu-id="c686a-170">""</span></span>  
  
-   <span data-ttu-id="c686a-171">"/shoe"</span><span class="sxs-lookup"><span data-stu-id="c686a-171">"/shoe"</span></span>  
  
-   <span data-ttu-id="c686a-172">"/shoe/\*"</span><span class="sxs-lookup"><span data-stu-id="c686a-172">"/shoe/\*"</span></span>  
  
-   <span data-ttu-id="c686a-173">"{shoe}/boat"</span><span class="sxs-lookup"><span data-stu-id="c686a-173">"{shoe}/boat"</span></span>  
  
-   <span data-ttu-id="c686a-174">"{shoe}/{boat}/bed/{quilt}"</span><span class="sxs-lookup"><span data-stu-id="c686a-174">"{shoe}/{boat}/bed/{quilt}"</span></span>  
  
-   <span data-ttu-id="c686a-175">«shoe / {boat}»</span><span class="sxs-lookup"><span data-stu-id="c686a-175">"shoe/{boat}"</span></span>  
  
-   <span data-ttu-id="c686a-176">«shoe / {boat} / \*»</span><span class="sxs-lookup"><span data-stu-id="c686a-176">"shoe/{boat}/\*"</span></span>  
  
-   <span data-ttu-id="c686a-177">«shoe/boat? x = 2»</span><span class="sxs-lookup"><span data-stu-id="c686a-177">"shoe/boat?x=2"</span></span>  
  
-   <span data-ttu-id="c686a-178">«shoe / {boat}? x = {bed}»</span><span class="sxs-lookup"><span data-stu-id="c686a-178">"shoe/{boat}?x={bed}"</span></span>  
  
-   <span data-ttu-id="c686a-179">"shoe/{boat}?x={bed}&y=band"</span><span class="sxs-lookup"><span data-stu-id="c686a-179">"shoe/{boat}?x={bed}&y=band"</span></span>  
  
-   <span data-ttu-id="c686a-180">«? x = {shoe}»</span><span class="sxs-lookup"><span data-stu-id="c686a-180">"?x={shoe}"</span></span>  
  
-   <span data-ttu-id="c686a-181">"shoe?x=3&y={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-181">"shoe?x=3&y={var}</span></span>  
  
 <span data-ttu-id="c686a-182">Ниже приведены недопустимые строки шаблона:</span><span class="sxs-lookup"><span data-stu-id="c686a-182">Examples of invalid template strings:</span></span>  
  
-   <span data-ttu-id="c686a-183">«{shoe} / {SHOE} / x = 2» – совпадающие имена переменных.</span><span class="sxs-lookup"><span data-stu-id="c686a-183">"{shoe}/{SHOE}/x=2" – Duplicate variable names.</span></span>  
  
-   <span data-ttu-id="c686a-184">«{shoe} /boat/? bed = {shoe}» – совпадающие имена переменных.</span><span class="sxs-lookup"><span data-stu-id="c686a-184">"{shoe}/boat/?bed={shoe}" – Duplicate variable names.</span></span>  
  
-   <span data-ttu-id="c686a-185">«? x = 2 & x = 3»-пары имя/значение в строке запроса должны быть уникальными, даже если они являются литералами.</span><span class="sxs-lookup"><span data-stu-id="c686a-185">"?x=2&x=3" – Name/value pairs within a query string must be unique, even if they are literals.</span></span>  
  
-   <span data-ttu-id="c686a-186">«? x = 2 &»-строка запроса имеет неправильный формат.</span><span class="sxs-lookup"><span data-stu-id="c686a-186">"?x=2&" – Query string is malformed.</span></span>  
  
-   <span data-ttu-id="c686a-187">«? 2 & x = {shoe}»-строка запроса должна состоять пары имя/значение.</span><span class="sxs-lookup"><span data-stu-id="c686a-187">"?2&x={shoe}" – Query string must be name/value pairs.</span></span>  
  
-   <span data-ttu-id="c686a-188">«? y = 2 & & X = 3»-строка запроса должна иметь пары "имя-значение", имена не могут начинаться с «&».</span><span class="sxs-lookup"><span data-stu-id="c686a-188">"?y=2&&X=3" – Query string must be name value pairs, names cannot start with '&'.</span></span>  
  
### <a name="compound-path-segments"></a><span data-ttu-id="c686a-189">Составные сегменты пути</span><span class="sxs-lookup"><span data-stu-id="c686a-189">Compound Path Segments</span></span>  
 <span data-ttu-id="c686a-190">Составные сегменты пути позволяют включать в один сегмент пути универсального кода ресурса (URI) несколько переменных, а также несколько переменных совместно с литералами.</span><span class="sxs-lookup"><span data-stu-id="c686a-190">Compound path segments allow a single URI path segment to contain multiple variables as well as variables combined with literals.</span></span> <span data-ttu-id="c686a-191">Ниже приведены примеры допустимых составных сегментов пути:</span><span class="sxs-lookup"><span data-stu-id="c686a-191">The following are examples of valid compound path segments.</span></span>  
  
-   <span data-ttu-id="c686a-192">/имя_файла.{ext}/</span><span class="sxs-lookup"><span data-stu-id="c686a-192">/filename.{ext}/</span></span>  
  
-   <span data-ttu-id="c686a-193">/{filename}.jpg/</span><span class="sxs-lookup"><span data-stu-id="c686a-193">/{filename}.jpg/</span></span>  
  
-   <span data-ttu-id="c686a-194">/{filename}.{ext}/</span><span class="sxs-lookup"><span data-stu-id="c686a-194">/{filename}.{ext}/</span></span>  
  
-   <span data-ttu-id="c686a-195">/{a}.{b}некоторый_литерал{c}({d})/</span><span class="sxs-lookup"><span data-stu-id="c686a-195">/{a}.{b}someLiteral{c}({d})/</span></span>  
  
 <span data-ttu-id="c686a-196">Ниже приведены примеры недопустимых составных сегментов пути.</span><span class="sxs-lookup"><span data-stu-id="c686a-196">The following are examples of invalid path segments.</span></span>  
  
-   <span data-ttu-id="c686a-197">/{} - переменная должна иметь имя.</span><span class="sxs-lookup"><span data-stu-id="c686a-197">/{} - Variables must be named.</span></span>  
  
-   <span data-ttu-id="c686a-198">/{shoe}{boat} - переменные должны разделяться литералом.</span><span class="sxs-lookup"><span data-stu-id="c686a-198">/{shoe}{boat} - Variables must be separated by a literal.</span></span>  
  
### <a name="matching-and-compound-path-segments"></a><span data-ttu-id="c686a-199">Совпадающие и составные сегменты пути</span><span class="sxs-lookup"><span data-stu-id="c686a-199">Matching and Compound Path Segments</span></span>  
 <span data-ttu-id="c686a-200">Составные сегменты пути позволяют определять UriTemplate, который имеет несколько переменных в одном сегменте пути.</span><span class="sxs-lookup"><span data-stu-id="c686a-200">Compound path segments allow you to define a UriTemplate that has multiple variables within a single path segment.</span></span> <span data-ttu-id="c686a-201">Например, в следующую строку шаблона: «адреса / {штат}. {city}» в одном сегменте определены две переменные (штату и городу).</span><span class="sxs-lookup"><span data-stu-id="c686a-201">For example, in the following template string: "Addresses/{state}.{city}" two variables (state and city) are defined within the same segment.</span></span> <span data-ttu-id="c686a-202">Этот шаблон будет соответствовать URL-адрес "http://example.com/Washington.Redmond«, но он также будет соответствовать URL, например»http://example.com/Washington.Redmond.Microsoft».</span><span class="sxs-lookup"><span data-stu-id="c686a-202">This template would match a URL such as "http://example.com/Washington.Redmond" but it will also match an URL like "http://example.com/Washington.Redmond.Microsoft".</span></span> <span data-ttu-id="c686a-203">В последнем случае переменная состояния будет содержать «Вашингтон», а переменная Город» будет содержать «Redmond.Microsoft».</span><span class="sxs-lookup"><span data-stu-id="c686a-203">In the latter case, the state variable will contain "Washington" and the city variable will contain "Redmond.Microsoft".</span></span> <span data-ttu-id="c686a-204">В данном случае любой текст (за исключением символа «/») будет соответствовать переменной {город}.</span><span class="sxs-lookup"><span data-stu-id="c686a-204">In this case any text (except ‘/’) will match the {city} variable.</span></span> <span data-ttu-id="c686a-205">Если требуется шаблон, который не будет соответствовать «дополнительному» тексту, поместите переменную в отдельный сегмент шаблона, например: «адреса / {штат} / {city}.</span><span class="sxs-lookup"><span data-stu-id="c686a-205">If you want a template that will not match the "extra" text, place the variable in a separate template segment, for example: "Addresses/{state}/{city}.</span></span>  
  
### <a name="named-wildcard-segments"></a><span data-ttu-id="c686a-206">Именованные сегменты с подстановочным знаком</span><span class="sxs-lookup"><span data-stu-id="c686a-206">Named Wildcard Segments</span></span>  
 <span data-ttu-id="c686a-207">Именованный сегмент с подстановочным знаком - это любой переменный сегмент, имя переменной которого начинается с символа-шаблона «\*».</span><span class="sxs-lookup"><span data-stu-id="c686a-207">A named wildcard segment is any path variable segment whose variable name begins with the wildcard character ‘\*’.</span></span> <span data-ttu-id="c686a-208">Следующая строка шаблона содержит именованный сегмент с подстановочным знаком, имеющий имя «shoe».</span><span class="sxs-lookup"><span data-stu-id="c686a-208">The following template string contains a named wildcard segment named "shoe".</span></span>  
  
```  
"literal/{*shoe}"  
```  
  
 <span data-ttu-id="c686a-209">Сегменты с подстановочными знаками должны удовлетворять следующим правилам.</span><span class="sxs-lookup"><span data-stu-id="c686a-209">Wildcard segments must follow the following rules:</span></span>  
  
-   <span data-ttu-id="c686a-210">В каждой строке шаблона должно быть не более одного именованного сегмента с подстановочным знаком.</span><span class="sxs-lookup"><span data-stu-id="c686a-210">There can be at most one named wildcard segment for each template string.</span></span>  
  
-   <span data-ttu-id="c686a-211">Именованный сегмент с подстановочным знаком должен быть самым правым сегментом пути.</span><span class="sxs-lookup"><span data-stu-id="c686a-211">A named wildcard segment must appear at the right-most segment in the path.</span></span>  
  
-   <span data-ttu-id="c686a-212">Именованный сегмент с подстановочным знаком и анонимный сегмент с подстановочным знаком не могут одновременно использоваться в одной строке шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-212">A named wildcard segment cannot coexist with an anonymous wildcard segment within the same template string.</span></span>  
  
-   <span data-ttu-id="c686a-213">Имя именованного сегмента с подстановочным знаком должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="c686a-213">The name of a named wildcard segment must be unique.</span></span>  
  
-   <span data-ttu-id="c686a-214">Именованные сегменты с подстановочным знаком не могут иметь значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c686a-214">Named wildcard segments cannot have default values.</span></span>  
  
-   <span data-ttu-id="c686a-215">Сегменты с подстановочными знаками именованный не может заканчиваться символом «/».</span><span class="sxs-lookup"><span data-stu-id="c686a-215">Named wildcard segments cannot end with "/".</span></span>  
  
### <a name="default-variable-values"></a><span data-ttu-id="c686a-216">Значения переменных по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c686a-216">Default Variable Values</span></span>  
 <span data-ttu-id="c686a-217">Значения переменных по умолчанию позволяют задавать значения по умолчанию для переменных шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-217">Default variable values allow you to specify default values for variables within a template.</span></span> <span data-ttu-id="c686a-218">Значения переменных по умолчанию могут быть заданы в фигурных скобках, объявляющих переменную, или в виде коллекции, передаваемой конструктору UriTemplate.</span><span class="sxs-lookup"><span data-stu-id="c686a-218">Default variables can be specified with the curly braces that declare the variable or as a collection passed to the UriTemplate constructor.</span></span> <span data-ttu-id="c686a-219">В следующем шаблоне показаны два способа задания <xref:System.UriTemplate> с переменными, имеющими значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c686a-219">The following template shows two ways to specify a <xref:System.UriTemplate> with variables with default values.</span></span>  
  
```  
UriTemplate t = new UriTemplate("/test/{a=1}/{b=5}");  
```  
  
 <span data-ttu-id="c686a-220">В этом шаблоне объявляются переменная с именем `a` и значением по умолчанию `1` и переменная с именем `b` со значением по умолчанию `5`.</span><span class="sxs-lookup"><span data-stu-id="c686a-220">This template declares a variable named `a` with a default value of `1` and a variable named `b` with a default value of `5`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c686a-221">Значения по умолчанию могут иметь только переменные сегмента пути.</span><span class="sxs-lookup"><span data-stu-id="c686a-221">Only path segment variables are allowed to have default values.</span></span> <span data-ttu-id="c686a-222">Переменные строки запроса, переменные составного сегмента и именованные переменные с подстановочным знаком не могут иметь значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c686a-222">Query string variables, compound segment variables, and named wildcard variables are not permitted to have default values.</span></span>  
  
 <span data-ttu-id="c686a-223">В следующем коде показано, как обрабатываются значения переменных по умолчанию при сопоставлении потенциального универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-223">The following code shows how default variable values are handled when matching a candidate URI.</span></span>  
  
```  
Uri baseAddress = new Uri("http://localhost:800   
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);0");  
UriTemplate t = new UriTemplate("/{state=WA}/{city=Redmond}/", true);  
Uri candidate = new Uri("http://localhost:8000/OR");  
  
UriTemplateMatch m1 = t.Match(baseAddress, candidate);  
  
// Display contents of BoundVariables  
foreach (string key in m1.BoundVariables.AllKeys)  
{  
    Console.WriteLine("\t\t{0}={1}", key, m1.BoundVariables[key]);  
}  
// The output of the above code is  
// Template: /{state=WA}/{city=Redmond}/  
// Candidate URI: http://localhost:8000/OR  
// BoundVariables:  
//      STATE=OR  
//       CITY=Redmond  
```  
  
> [!NOTE]
>  <span data-ttu-id="c686a-224">URI вида http://localhost:8000/// не соответствует шаблону, указанному в приведенном выше коде, в отличие от URI вида http://localhost:8000/.</span><span class="sxs-lookup"><span data-stu-id="c686a-224">A URI such as http://localhost:8000/// does not match the template listed in the preceding code, however a URI such as http://localhost:8000/ does.</span></span>  
  
 <span data-ttu-id="c686a-225">В следующем коде показано, как обрабатываются значения переменных по умолчанию при создании универсального кода ресурса (URI) с помощью шаблона.</span><span class="sxs-lookup"><span data-stu-id="c686a-225">The following code shows how default variable values are handled when creating a URI with a template.</span></span>  
  
```  
Uri baseAddress = new Uri("http://localhost:8000/");  
Dictionary<string,string> defVals = new Dictionary<string,string> {{"a","1"}, {"b", "5"}};  
UriTemplate t = new UriTemplate("/test/{a}/{b}", defVals);  
NameValueCollection vals = new NameValueCollection();  
vals.Add("a", "10");  
  
Uri boundUri = t.BindByName(baseAddress, vals);  
Console.WriteLine("BaseAddress: {0}", baseAddress);  
Console.WriteLine("Template: {0}", t.ToString());  
  
Console.WriteLine("Values: ");  
foreach (string key in vals.AllKeys)  
{  
    Console.WriteLine("\tKey = {0}, Value = {1}", key, vals[key]);  
}  
Console.WriteLine("Bound URI: {0}", boundUri);  
  
// The output of the preceding code is  
// BaseAddress: http://localhost:8000/  
// Template: /test/{a}/{b}  
// Values:  
//     Key = a, Value = 10  
// Bound URI: http://localhost:8000/test/10/5  
```  
  
 <span data-ttu-id="c686a-226">Если переменной присвоено значение по умолчанию `null`, существуют дополнительные ограничения.</span><span class="sxs-lookup"><span data-stu-id="c686a-226">When a variable is given a default value of `null` there are some additional constraints.</span></span> <span data-ttu-id="c686a-227">Переменная может иметь значение по умолчанию `null`, если эта переменная содержится в самом правом сегменте строки шаблона или если все сегменты справа от этого сегмента имеют значения по умолчанию `null`.</span><span class="sxs-lookup"><span data-stu-id="c686a-227">A variable can have a default value of `null` if the variable is contained within the right most segment of the template string or if all segments to the right of the segment have default values of `null`.</span></span> <span data-ttu-id="c686a-228">Ниже приводятся допустимые строки шаблона со значениями по умолчанию `null`:</span><span class="sxs-lookup"><span data-stu-id="c686a-228">The following are valid template strings with default values of `null`:</span></span>  
  
-   ```  
    UriTemplate t = new UriTemplate("shoe/{boat=null}");  
    ```  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=null}");  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=1}/{boat=null}");  
    ```  
 <span data-ttu-id="c686a-229">Ниже приводятся недопустимые строки шаблона со значениями по умолчанию `null`:</span><span class="sxs-lookup"><span data-stu-id="c686a-229">The following are invalid template strings with  default values of `null`:</span></span>  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/boat"); // null default must be in the right most path segment  
    ```  
  
-   ```  
    UriTemplate t = new UriTemplate("{shoe=null}/{boat=x}/{bed=null}"); // shoe cannot have a null default because boat does not have a default null value  
    ```  
### <a name="default-values-and-matching"></a><span data-ttu-id="c686a-230">Значения по умолчанию и сопоставление</span><span class="sxs-lookup"><span data-stu-id="c686a-230">Default Values and Matching</span></span>  
 <span data-ttu-id="c686a-231">При сопоставлении URI-кандидата с шаблоном, имеющим значения по умолчанию, в коллекцию <xref:System.UriTemplateMatch.BoundVariables%2A> помещаются значения по умолчанию, если в URI-кандидате не указаны значения.</span><span class="sxs-lookup"><span data-stu-id="c686a-231">When matching a candidate URI with a template that has default values, the default values are placed in the <xref:System.UriTemplateMatch.BoundVariables%2A> collection if values are not specified in the candidate URI.</span></span>  
  
### <a name="template-equivalence"></a><span data-ttu-id="c686a-232">Эквивалентность шаблонов</span><span class="sxs-lookup"><span data-stu-id="c686a-232">Template Equivalence</span></span>  
 <span data-ttu-id="c686a-233">Два шаблона называются *структурно эквивалентных* при соответствии всем литералы и переменные находятся в одинаковых сегментах.</span><span class="sxs-lookup"><span data-stu-id="c686a-233">Two templates are said to be *structurally equivalent* when all of the templates' literals match and they have variables in the same segments.</span></span> <span data-ttu-id="c686a-234">Например, указанные ниже шаблоны структурно эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="c686a-234">For example the following templates are structurally equivalent:</span></span>  
  
-   <span data-ttu-id="c686a-235">/a/{var1}/b b/{var2}?x=1&y=2</span><span class="sxs-lookup"><span data-stu-id="c686a-235">/a/{var1}/b b/{var2}?x=1&y=2</span></span>  
  
-   <span data-ttu-id="c686a-236">a/{x}/b%20b/{var1}?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-236">a/{x}/b%20b/{var1}?y=2&x=1</span></span>  
  
-   <span data-ttu-id="c686a-237">a/{y}/B%20B/{z}/?y=2&x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-237">a/{y}/B%20B/{z}/?y=2&x=1</span></span>  
  
 <span data-ttu-id="c686a-238">Некоторые замечания.</span><span class="sxs-lookup"><span data-stu-id="c686a-238">A few things to notice:</span></span>  
  
-   <span data-ttu-id="c686a-239">Если шаблон содержит начальные символы косой черты, игнорируется только первый из них.</span><span class="sxs-lookup"><span data-stu-id="c686a-239">If a template contains leading slashes, only the first one is ignored.</span></span>  
  
-   <span data-ttu-id="c686a-240">При сравнении строк шаблона для определения их структурной эквивалентности регистр пропускается для имен переменных и сегментов пути, в строках запроса регистр учитывается.</span><span class="sxs-lookup"><span data-stu-id="c686a-240">When comparing template strings for structural equivalence, case is ignored for variable names and path segments, query strings are case sensitive.</span></span>  
  
-   <span data-ttu-id="c686a-241">Строки запроса неупорядочены.</span><span class="sxs-lookup"><span data-stu-id="c686a-241">Query strings are unordered.</span></span>  
  
## <a name="uritemplatetable"></a><span data-ttu-id="c686a-242">UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="c686a-242">UriTemplateTable</span></span>  
 <span data-ttu-id="c686a-243">Класс <xref:System.UriTemplateTable> представляет ассоциативную таблицу объектов <xref:System.UriTemplate>, привязанных к объекту, выбранному разработчиком.</span><span class="sxs-lookup"><span data-stu-id="c686a-243">The <xref:System.UriTemplateTable> class represents an associative table of <xref:System.UriTemplate> objects bound to an object of the developer's choosing.</span></span> <span data-ttu-id="c686a-244">Класс <xref:System.UriTemplateTable> должен содержать по крайней мере один объект <xref:System.UriTemplate>, чтобы можно было вызвать метод <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c686a-244">A <xref:System.UriTemplateTable> must contain at least one <xref:System.UriTemplate> prior to calling <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span> <span data-ttu-id="c686a-245">Содержимое таблицы <xref:System.UriTemplateTable> можно изменять до тех пор, пока не будет вызван метод <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c686a-245">The contents of a <xref:System.UriTemplateTable> can be changed until <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="c686a-246">Проверка выполняется при вызове метода <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c686a-246">Validation is performed when <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called.</span></span> <span data-ttu-id="c686a-247">Тип выполняемой проверки зависит от значения параметра `allowMultiple` метода <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span><span class="sxs-lookup"><span data-stu-id="c686a-247">The type of validation performed depends upon the value of the `allowMultiple` parameter to <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29>.</span></span>  
  
 <span data-ttu-id="c686a-248">Если при вызове метода <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> ему передается значение `false`, таблица <xref:System.UriTemplateTable> проверяется, чтобы убедиться, что в ней отсутствуют шаблоны.</span><span class="sxs-lookup"><span data-stu-id="c686a-248">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `false`, the <xref:System.UriTemplateTable> checks to make sure there are no templates in the table.</span></span> <span data-ttu-id="c686a-249">Если будут найдены какие-либо структурно эквивалентные шаблоны, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="c686a-249">If it finds any structurally equivalent templates, it throws an exception.</span></span> <span data-ttu-id="c686a-250">Это используется совместно с методом <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29>, если требуется обеспечить, чтобы только один шаблон соответствовал входящему универсальному коду ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="c686a-250">This is used in conjunction with <xref:System.UriTemplateTable.MatchSingle%28System.Uri%29> when you want to ensure only one template matches an incoming URI.</span></span>  
  
 <span data-ttu-id="c686a-251">Если при выборе метода <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> ему передается значение `true`, <xref:System.UriTemplateTable> допускает наличии нескольких структурно эквивалентных шаблонов в <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="c686a-251">When <xref:System.UriTemplateTable.MakeReadOnly%28System.Boolean%29> is called passing in `true`, <xref:System.UriTemplateTable> allows multiple, structurally-equivalent templates to be contained within a <xref:System.UriTemplateTable>.</span></span>  
  
 <span data-ttu-id="c686a-252">Если набор объектов <xref:System.UriTemplate>, добавленных в таблицу <xref:System.UriTemplateTable>, содержит строки запроса, они не должны быть неоднозначными.</span><span class="sxs-lookup"><span data-stu-id="c686a-252">If a set of <xref:System.UriTemplate> objects added to a <xref:System.UriTemplateTable> contain query strings they must not be ambiguous.</span></span> <span data-ttu-id="c686a-253">Допускаются идентичные строки запросов.</span><span class="sxs-lookup"><span data-stu-id="c686a-253">Identical query strings are allowed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c686a-254">Хотя <xref:System.UriTemplateTable> допускает базовые адреса, использующие схемы, отличные от HTTP, при сопоставлении потенциальных универсальных кодов ресурсов (URI) с шаблонами схема и номер порта пропускаются.</span><span class="sxs-lookup"><span data-stu-id="c686a-254">While the <xref:System.UriTemplateTable> allows base addresses that use schemes other than HTTP, the scheme and port number are ignored when matching candidate URIs to templates.</span></span>  
  
### <a name="query-string-ambiguity"></a><span data-ttu-id="c686a-255">Неоднозначность строки запроса</span><span class="sxs-lookup"><span data-stu-id="c686a-255">Query String Ambiguity</span></span>  
 <span data-ttu-id="c686a-256">Шаблоны, содержащие эквивалентные пути, содержат неоднозначные строки запроса, если существует универсальный код ресурса (URI), соответствующий нескольким шаблонам.</span><span class="sxs-lookup"><span data-stu-id="c686a-256">Templates that share an equivalent path contain ambiguous query strings if there is a URI that matches more than one template.</span></span>  
  
 <span data-ttu-id="c686a-257">Приведенные ниже наборы строк запроса однозначны внутри себя.</span><span class="sxs-lookup"><span data-stu-id="c686a-257">The following sets of query strings are unambiguous within themselves:</span></span>  
  
-   <span data-ttu-id="c686a-258">?x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-258">?x=1</span></span>  
  
-   <span data-ttu-id="c686a-259">?x=2</span><span class="sxs-lookup"><span data-stu-id="c686a-259">?x=2</span></span>  
  
-   <span data-ttu-id="c686a-260">?x=3</span><span class="sxs-lookup"><span data-stu-id="c686a-260">?x=3</span></span>  
  
-   <span data-ttu-id="c686a-261">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-261">?x=1&y={var}</span></span>  
  
-   <span data-ttu-id="c686a-262">?x=2&z={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-262">?x=2&z={var}</span></span>  
  
-   <span data-ttu-id="c686a-263">?x=3</span><span class="sxs-lookup"><span data-stu-id="c686a-263">?x=3</span></span>  
  
-   <span data-ttu-id="c686a-264">?x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-264">?x=1</span></span>  
  
-   <span data-ttu-id="c686a-265">?</span><span class="sxs-lookup"><span data-stu-id="c686a-265">?</span></span>  
  
-   <span data-ttu-id="c686a-266">?</span><span class="sxs-lookup"><span data-stu-id="c686a-266">?</span></span> <span data-ttu-id="c686a-267">x={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-267">x={var}</span></span>  
  
-   <span data-ttu-id="c686a-268">?</span><span class="sxs-lookup"><span data-stu-id="c686a-268">?</span></span>  
  
-   <span data-ttu-id="c686a-269">?m=get&c=rss</span><span class="sxs-lookup"><span data-stu-id="c686a-269">?m=get&c=rss</span></span>  
  
-   <span data-ttu-id="c686a-270">?m=put&c=rss</span><span class="sxs-lookup"><span data-stu-id="c686a-270">?m=put&c=rss</span></span>  
  
-   <span data-ttu-id="c686a-271">?m=get&c=atom</span><span class="sxs-lookup"><span data-stu-id="c686a-271">?m=get&c=atom</span></span>  
  
-   <span data-ttu-id="c686a-272">?m=put&c=atom</span><span class="sxs-lookup"><span data-stu-id="c686a-272">?m=put&c=atom</span></span>  
  
 <span data-ttu-id="c686a-273">Приведенные ниже шаблоны строк запроса неоднозначны внутри себя.</span><span class="sxs-lookup"><span data-stu-id="c686a-273">The following sets of query string templates are ambiguous within themselves:</span></span>  
  
-   <span data-ttu-id="c686a-274">?x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-274">?x=1</span></span>  
  
-   <span data-ttu-id="c686a-275">?x={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-275">?x={var}</span></span>  
  
 <span data-ttu-id="c686a-276">"x=1" — соответствует обеим шаблонам.</span><span class="sxs-lookup"><span data-stu-id="c686a-276">"x=1" - Matches both templates.</span></span>  
  
-   <span data-ttu-id="c686a-277">?x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-277">?x=1</span></span>  
  
-   <span data-ttu-id="c686a-278">?y=2</span><span class="sxs-lookup"><span data-stu-id="c686a-278">?y=2</span></span>  
  
 <span data-ttu-id="c686a-279">Строка "x=1&y=2" соответствует обоим шаблонам.</span><span class="sxs-lookup"><span data-stu-id="c686a-279">"x=1&y=2" matches both templates.</span></span> <span data-ttu-id="c686a-280">Это связано с тем, что строка запроса может содержать больше переменных стоки запроса, чем соответствующий ей шаблон.</span><span class="sxs-lookup"><span data-stu-id="c686a-280">This is because a query string may contain more query string variables then the template it matches.</span></span>  
  
-   <span data-ttu-id="c686a-281">?x=1</span><span class="sxs-lookup"><span data-stu-id="c686a-281">?x=1</span></span>  
  
-   <span data-ttu-id="c686a-282">?x=1&y={var}</span><span class="sxs-lookup"><span data-stu-id="c686a-282">?x=1&y={var}</span></span>  
  
 <span data-ttu-id="c686a-283">Строка "x=1&y=3" соответствует обоим шаблонам.</span><span class="sxs-lookup"><span data-stu-id="c686a-283">"x=1&y=3" matches both templates.</span></span>  
  
-   <span data-ttu-id="c686a-284">?x=3&y=4</span><span class="sxs-lookup"><span data-stu-id="c686a-284">?x=3&y=4</span></span>  
  
-   <span data-ttu-id="c686a-285">?x=3&z=5</span><span class="sxs-lookup"><span data-stu-id="c686a-285">?x=3&z=5</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c686a-286">Буквы "á" и "Á" считаются разными символами, если они используются в пути универсального кода ресурса (URI) или в литерале сегмента пути <xref:System.UriTemplate> (но буквы "a" и "A" считаются одинаковыми).</span><span class="sxs-lookup"><span data-stu-id="c686a-286">The characters á and Á are considered to be different characters when they appear as part of a URI path or <xref:System.UriTemplate> path segment literal (but the characters a and A are considered to be the same).</span></span> <span data-ttu-id="c686a-287">Буквы "á" и "Á" считаются одинаковыми символами, если они используются в <xref:System.UriTemplate> {имя_переменной} или строке запроса (а буквы "a" и "A" также считаются одинаковыми).</span><span class="sxs-lookup"><span data-stu-id="c686a-287">The characters á and Á are considered to be the same characters when they appear as part of a <xref:System.UriTemplate> {variableName} or a query string (and a and A are also considered to be the same characters).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c686a-288">См. также</span><span class="sxs-lookup"><span data-stu-id="c686a-288">See Also</span></span>  
 [<span data-ttu-id="c686a-289">Общие сведения о модели веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="c686a-289">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 [<span data-ttu-id="c686a-290">Объектная модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="c686a-290">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 [<span data-ttu-id="c686a-291">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c686a-291">UriTemplate</span></span>](../../../../docs/framework/wcf/samples/uritemplate-sample.md)  
 [<span data-ttu-id="c686a-292">Таблица UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c686a-292">UriTemplate Table</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)  
 [<span data-ttu-id="c686a-293">Диспетчер таблицы UriTemplate</span><span class="sxs-lookup"><span data-stu-id="c686a-293">UriTemplate Table Dispatcher</span></span>](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
