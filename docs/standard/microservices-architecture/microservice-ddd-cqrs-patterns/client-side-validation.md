---
title: "Проверки на стороне клиента (проверка слоев presentation)"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Проверки на стороне клиента (проверка слоев presentation)"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="a97c8-104">Проверки на стороне клиента (проверка слоев presentation)</span><span class="sxs-lookup"><span data-stu-id="a97c8-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="a97c8-105">Даже в том случае, если источник достоверных является моделью домена и в конечном счете должен иметь проверки на уровне модели домена, проверки по-прежнему может быть обработано на уровне модели домена (на стороне сервера) и на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="a97c8-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="a97c8-106">Проверка на стороне клиента является большое удобство для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a97c8-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="a97c8-107">Она сохраняет время, в противном случае они бы проводят ожидание кругового пути к серверу, могут возвращать ошибки проверки.</span><span class="sxs-lookup"><span data-stu-id="a97c8-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="a97c8-108">Бизнес-терминологией даже несколько долей секунды, умноженные сотни раз в день складываются много времени, затрат и трудностей.</span><span class="sxs-lookup"><span data-stu-id="a97c8-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="a97c8-109">Простой и непосредственный проверки позволяет пользователям работать более продуктивно и создавать более высокое качество входных и выходных данных.</span><span class="sxs-lookup"><span data-stu-id="a97c8-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="a97c8-110">Так же, как модели представления и модель домена не совпадают, проверка модели представления и проверка модели домена может выглядеть следующим образом, но выполняют различные функции.</span><span class="sxs-lookup"><span data-stu-id="a97c8-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="a97c8-111">Если вы сомневаетесь о ПРОБНОГО (не повторяться принцип) полагать, что в этом случае повторное использование кода также может означать связь, в корпоративных приложениях важнее не привязать стороне сервера на клиентской стороне, чем для выполните ТОНЕРА принцип.</span><span class="sxs-lookup"><span data-stu-id="a97c8-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="a97c8-112">Даже при использовании проверки на стороне клиента, следует всегда проверки команды или ввода DTO в серверном коде, так как сервер API-интерфейсы возможных атак.</span><span class="sxs-lookup"><span data-stu-id="a97c8-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="a97c8-113">Обычно этого не лучшим решением, так как при наличии клиентского приложения, с точки зрения взаимодействия с Пользователем, лучше всего упреждающие и позволяет пользователю ввести недопустимые данные.</span><span class="sxs-lookup"><span data-stu-id="a97c8-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="a97c8-114">Таким образом в код на стороне клиента обычно проверки ViewModels.</span><span class="sxs-lookup"><span data-stu-id="a97c8-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="a97c8-115">Можно также проверить клиента вывода DTO или команды, перед отправкой в службы.</span><span class="sxs-lookup"><span data-stu-id="a97c8-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="a97c8-116">Реализация проверки на стороне клиента зависит от того, какого рода клиентское приложение выполняется построение.</span><span class="sxs-lookup"><span data-stu-id="a97c8-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="a97c8-117">Он будет отличаться при проверке данных на веб-узле веб-приложение MVC с помощью большая часть кода в .NET, веб-приложение SPA с проверки закодированные на языке JavaScript или TypeScript, или мобильного приложения, закодированных с помощью Xamarin и C\#.</span><span class="sxs-lookup"><span data-stu-id="a97c8-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a97c8-118">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="a97c8-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="a97c8-119">Проверка данных в мобильных приложениях Xamarin</span><span class="sxs-lookup"><span data-stu-id="a97c8-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="a97c8-120">**Проверка ввода текста и Показать ошибки**
    [*https://developer.xamarin.com/recipes/ios/standard\_элементов управления и текста\_поля и проверки\_входной /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="a97c8-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="a97c8-121">**Обратный вызов проверки**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="a97c8-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="a97c8-122">Проверка данных в приложениях ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a97c8-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="a97c8-123">**Рик Андерсон (Rick Anderson). Добавление проверки**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="a97c8-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="a97c8-124">Проверка в SPA веб-приложений (углового 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="a97c8-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="a97c8-125">**ADO Kukic. Проверка формы углового 2** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="a97c8-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="a97c8-126">**Проверка формы**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="a97c8-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="a97c8-127">**Проверка.**</span><span class="sxs-lookup"><span data-stu-id="a97c8-127">**Validation.**</span></span> <span data-ttu-id="a97c8-128">Просто документации.</span><span class="sxs-lookup"><span data-stu-id="a97c8-128">Breeze documentation.</span></span>
    [<span data-ttu-id="a97c8-129">*http://breeze.github.IO/doc-js/Validation.HTML*</span><span class="sxs-lookup"><span data-stu-id="a97c8-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="a97c8-130">Таким образом это наиболее важных понятий в отношении проверки:</span><span class="sxs-lookup"><span data-stu-id="a97c8-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="a97c8-131">Сущности и статистические функции должны обеспечивать согласованность своих собственных и действовать «всегда».</span><span class="sxs-lookup"><span data-stu-id="a97c8-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="a97c8-132">Агрегатные корни отвечают согласованность нескольких сущностей в одной агрегатной функции.</span><span class="sxs-lookup"><span data-stu-id="a97c8-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="a97c8-133">Если вы считаете, что сущности необходимо ввести недопустимое состояние, рассмотрите возможность использования различных объектной модели, например, с помощью временного DTO, пока не будет создана сущность конечного домена.</span><span class="sxs-lookup"><span data-stu-id="a97c8-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="a97c8-134">Если необходимо создать несколько связанных объектов, таких как агрегатную функцию, и они допустимы только если все они были созданы, рассмотрите возможность использования шаблона фабрики.</span><span class="sxs-lookup"><span data-stu-id="a97c8-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="a97c8-135">Проверки платформы лучше использовать в определенных уровней, таких как уровень представления данных или уровня приложения или службы, но обычно не на уровне модели домена, поскольку необходимо установить надежный зависимость платформу инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="a97c8-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="a97c8-136">В большинстве случаев с дополнительную проверку на стороне клиента подходит, так как приложение может быть упреждающего.</span><span class="sxs-lookup"><span data-stu-id="a97c8-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a97c8-137">[Предыдущие] (домен модели слоя validations.md) [Далее] (домен события конструктора implementation.md)</span><span class="sxs-lookup"><span data-stu-id="a97c8-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
