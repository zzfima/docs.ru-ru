---
title: Проверка на стороне клиента (проверка на уровнях представления)
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Проверка на стороне клиента (проверка на уровнях представления)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 2adce39561dd2b97910155ebed595a2df7785c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="02050-103">Проверка на стороне клиента (проверка на уровнях представления)</span><span class="sxs-lookup"><span data-stu-id="02050-103">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="02050-104">Даже если источником истины является модель предметной области и в конечном итоге необходимо проводить проверки на этом уровне, проверку можно выполнить как на уровне модели предметной области (на сервере), так и на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="02050-104">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="02050-105">Проверка на стороне клиента очень удобна для пользователей.</span><span class="sxs-lookup"><span data-stu-id="02050-105">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="02050-106">Она экономит время, которое в противном случае тратилось бы на круговой путь к серверу, в результате которого выдавались бы ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="02050-106">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="02050-107">С точки зрения бизнеса даже доли секунды, умножаемые в сотни раз каждый день, позволяют значительно сократить расходуемое время, деньги и усилия.</span><span class="sxs-lookup"><span data-stu-id="02050-107">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="02050-108">Простая и немедленная проверка позволяет пользователям работать эффективнее и повышает точность входных и выходных данных.</span><span class="sxs-lookup"><span data-stu-id="02050-108">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="02050-109">Так же как модель представления отличается от модели предметной области, проверка модели представления и проверка модели предметной области имеют сходные черты, но выполняют разные функции.</span><span class="sxs-lookup"><span data-stu-id="02050-109">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="02050-110">Если вы беспокоитесь о принципе DRY ("Не повторяйся"), то в этом случае повторное использование кода может означать взаимозависимость, а в корпоративном приложении взаимозависимость стороны сервера и стороны клиента гораздо хуже, чем нарушение принципа "Не повторяйся".</span><span class="sxs-lookup"><span data-stu-id="02050-110">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="02050-111">Даже при проведении проверки на стороне клиента следует всегда проверять команды или входящие объекты переноса данных в серверном коде, ведь API сервера являются возможным вектором атаки.</span><span class="sxs-lookup"><span data-stu-id="02050-111">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="02050-112">Как правило, рекомендуется выполнять обе проверки, поскольку, с точки зрения взаимодействия с пользователем, в клиентском приложении лучше действовать на опережение и не допускать ввод пользователем недопустимых данных.</span><span class="sxs-lookup"><span data-stu-id="02050-112">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="02050-113">Поэтому в коде на стороне клиенты вы обычно проверяете модели представления.</span><span class="sxs-lookup"><span data-stu-id="02050-113">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="02050-114">Можно также проверять исходящие объекты переноса данных или команды клиента, прежде чем отправлять их службам.</span><span class="sxs-lookup"><span data-stu-id="02050-114">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="02050-115">Выполнение проверки на стороне клиента зависит от типа создаваемого клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="02050-115">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="02050-116">Существуют отличия при проверке данных в веб-приложении MVC, где программирование по большей части осуществляется в .NET, веб-приложении SPA, где проверка написана на JavaScript или TypeScript, или в мобильном приложении с кодом на Xamarin и C\#.</span><span class="sxs-lookup"><span data-stu-id="02050-116">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02050-117">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="02050-117">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="02050-118">Проверка в мобильных приложениях Xamarin</span><span class="sxs-lookup"><span data-stu-id="02050-118">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="02050-119">**Проверка введенного текста и отображение ошибок**
    [*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="02050-119">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="02050-120">**Ответный вызов проверки**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="02050-120">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="02050-121">Проверка в приложениях ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02050-121">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="02050-122">**Рик Андерсон (Rick Anderson). Добавление проверки**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="02050-122">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="02050-123">Проверка в веб-приложениях SPA (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="02050-123">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="02050-124">**Адо Кукич (Ado Kukic). Проверка форм Angular 2** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="02050-124">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="02050-125">**Проверка форм**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="02050-125">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="02050-126">**Проверка.**</span><span class="sxs-lookup"><span data-stu-id="02050-126">**Validation.**</span></span> <span data-ttu-id="02050-127">Документация Breeze.</span><span class="sxs-lookup"><span data-stu-id="02050-127">Breeze documentation.</span></span>
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="02050-128">Подытожим основные принципы проверки:</span><span class="sxs-lookup"><span data-stu-id="02050-128">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="02050-129">Сущности и агрегаты должны обеспечивать собственную согласованность и всегда быть допустимыми.</span><span class="sxs-lookup"><span data-stu-id="02050-129">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="02050-130">Агрегатные корни отвечают за согласованность нескольких сущностей в одном агрегате.</span><span class="sxs-lookup"><span data-stu-id="02050-130">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="02050-131">Если вы считаете, что сущность должна входить в недопустимое состояние, подумайте об использовании другой объектной модели — например, используйте объект переноса данных до создания окончательной сущности предметной области.</span><span class="sxs-lookup"><span data-stu-id="02050-131">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="02050-132">Если необходимо создать несколько связанных объектов, например агрегат, и они будут допустимы только после создания всех объектов, используйте шаблон "фабрика".</span><span class="sxs-lookup"><span data-stu-id="02050-132">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="02050-133">Платформы проверки лучше использовать на определенных уровнях, например на уровне представления или уровне приложения или службы, но не на уровне модели предметной области, поскольку потребуется надежная зависимость от платформы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="02050-133">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="02050-134">В большинстве случаев избыточная проверка на стороне клиента уместна, ведь приложение может действовать на опережение.</span><span class="sxs-lookup"><span data-stu-id="02050-134">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="02050-135">[Назад] (domain-model-layer-validations.md) [Далее] (domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="02050-135">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
