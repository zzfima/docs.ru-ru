---
title: Проверка на стороне клиента (проверка на уровнях представления)
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Проверка на стороне клиента (проверка на уровнях представления)
keywords: Docker, микрослужбы, ASP.NET, контейнер
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 273aa0a8ceb7f683999f1074faae0a6aa303f9be
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="cefa2-104">Проверка на стороне клиента (проверка на уровнях представления)</span><span class="sxs-lookup"><span data-stu-id="cefa2-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="cefa2-105">Даже если источником истины является модель предметной области и в конечном итоге необходимо проводить проверки на этом уровне, проверку можно выполнить как на уровне модели предметной области (на сервере), так и на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="cefa2-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="cefa2-106">Проверка на стороне клиента очень удобна для пользователей.</span><span class="sxs-lookup"><span data-stu-id="cefa2-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="cefa2-107">Она экономит время, которое в противном случае тратилось бы на круговой путь к серверу, в результате которого выдавались бы ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="cefa2-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="cefa2-108">С точки зрения бизнеса даже доли секунды, умножаемые в сотни раз каждый день, позволяют значительно сократить расходуемое время, деньги и усилия.</span><span class="sxs-lookup"><span data-stu-id="cefa2-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="cefa2-109">Простая и немедленная проверка позволяет пользователям работать эффективнее и повышает точность входных и выходных данных.</span><span class="sxs-lookup"><span data-stu-id="cefa2-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="cefa2-110">Так же как модель представления отличается от модели предметной области, проверка модели представления и проверка модели предметной области имеют сходные черты, но выполняют разные функции.</span><span class="sxs-lookup"><span data-stu-id="cefa2-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="cefa2-111">Если вы беспокоитесь о принципе DRY ("Не повторяйся"), то в этом случае повторное использование кода может означать взаимозависимость, а в корпоративном приложении взаимозависимость стороны сервера и стороны клиента гораздо хуже, чем нарушение принципа "Не повторяйся".</span><span class="sxs-lookup"><span data-stu-id="cefa2-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="cefa2-112">Даже при проведении проверки на стороне клиента следует всегда проверять команды или входящие объекты переноса данных в серверном коде, ведь API сервера являются возможным вектором атаки.</span><span class="sxs-lookup"><span data-stu-id="cefa2-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="cefa2-113">Как правило, рекомендуется выполнять обе проверки, поскольку, с точки зрения взаимодействия с пользователем, в клиентском приложении лучше действовать на опережение и не допускать ввод пользователем недопустимых данных.</span><span class="sxs-lookup"><span data-stu-id="cefa2-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="cefa2-114">Поэтому в коде на стороне клиенты вы обычно проверяете модели представления.</span><span class="sxs-lookup"><span data-stu-id="cefa2-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="cefa2-115">Можно также проверять исходящие объекты переноса данных или команды клиента, прежде чем отправлять их службам.</span><span class="sxs-lookup"><span data-stu-id="cefa2-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="cefa2-116">Выполнение проверки на стороне клиента зависит от типа создаваемого клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="cefa2-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="cefa2-117">Существуют отличия при проверке данных в веб-приложении MVC, где программирование по большей части осуществляется в .NET, веб-приложении SPA, где проверка написана на JavaScript или TypeScript, или в мобильном приложении с кодом на Xamarin и C\#.</span><span class="sxs-lookup"><span data-stu-id="cefa2-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cefa2-118">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="cefa2-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="cefa2-119">Проверка в мобильных приложениях Xamarin</span><span class="sxs-lookup"><span data-stu-id="cefa2-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="cefa2-120">**Проверка ввода текста и Показать ошибки**
    [*https://developer.xamarin.com/recipes/ios/standard\_элементов управления и текста\_поля и проверки\_входной /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="cefa2-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="cefa2-121">**Обратный вызов проверки**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="cefa2-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="cefa2-122">Проверка в приложениях ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cefa2-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="cefa2-123">**Рик Андерсон (Rick Anderson). Добавление проверки**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="cefa2-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="cefa2-124">Проверка в веб-приложениях SPA (Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="cefa2-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="cefa2-125">**Адо Кукич (Ado Kukic). Угловое проверку формы 2** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="cefa2-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="cefa2-126">**Проверка формы**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="cefa2-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="cefa2-127">**Проверка.**</span><span class="sxs-lookup"><span data-stu-id="cefa2-127">**Validation.**</span></span> <span data-ttu-id="cefa2-128">Документация Breeze.</span><span class="sxs-lookup"><span data-stu-id="cefa2-128">Breeze documentation.</span></span>
    [*http://breeze.github.io/doc-js/validation.html*](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="cefa2-129">Подытожим основные принципы проверки:</span><span class="sxs-lookup"><span data-stu-id="cefa2-129">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="cefa2-130">Сущности и агрегаты должны обеспечивать собственную согласованность и всегда быть допустимыми.</span><span class="sxs-lookup"><span data-stu-id="cefa2-130">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="cefa2-131">Агрегатные корни отвечают за согласованность нескольких сущностей в одном агрегате.</span><span class="sxs-lookup"><span data-stu-id="cefa2-131">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="cefa2-132">Если вы считаете, что сущность должна входить в недопустимое состояние, подумайте об использовании другой объектной модели — например, используйте объект переноса данных до создания окончательной сущности предметной области.</span><span class="sxs-lookup"><span data-stu-id="cefa2-132">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="cefa2-133">Если необходимо создать несколько связанных объектов, например агрегат, и они будут допустимы только после создания всех объектов, используйте шаблон "фабрика".</span><span class="sxs-lookup"><span data-stu-id="cefa2-133">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="cefa2-134">Платформы проверки лучше использовать на определенных уровнях, например на уровне представления или уровне приложения или службы, но не на уровне модели предметной области, поскольку потребуется надежная зависимость от платформы инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="cefa2-134">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="cefa2-135">В большинстве случаев избыточная проверка на стороне клиента уместна, ведь приложение может действовать на опережение.</span><span class="sxs-lookup"><span data-stu-id="cefa2-135">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cefa2-136">[Назад] (domain-model-layer-validations.md) [Далее] (domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="cefa2-136">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
