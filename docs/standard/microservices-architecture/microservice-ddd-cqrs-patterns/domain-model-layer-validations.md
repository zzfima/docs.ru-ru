---
title: "Проектирование проверок в уровне модели домена"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Проектирование проверок в уровне модели домена"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="0e85e-104">Проектирование проверок в уровне модели домена</span><span class="sxs-lookup"><span data-stu-id="0e85e-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="0e85e-105">В ддд правила проверки можно рассматривать как инварианты.</span><span class="sxs-lookup"><span data-stu-id="0e85e-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="0e85e-106">Главной задачей статистической обработки является принудительное инварианты через изменения состояния для всех сущностей внутри сводные данные.</span><span class="sxs-lookup"><span data-stu-id="0e85e-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="0e85e-107">Сущности домена всегда должно быть допустимым сущностей.</span><span class="sxs-lookup"><span data-stu-id="0e85e-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="0e85e-108">Существует несколько вариантов для объекта, который всегда должен иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="0e85e-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="0e85e-109">Например объект элемента заказа всегда должен иметь количество, которое должно быть положительным целым числом, а также имя статьи и price.</span><span class="sxs-lookup"><span data-stu-id="0e85e-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="0e85e-110">Таким образом применение инварианты несет ответственность за сущностями домена (особенно для статистических root) и объект сущности не сможете использовать, не являются допустимыми.</span><span class="sxs-lookup"><span data-stu-id="0e85e-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="0e85e-111">Инвариантные правила просто выражаются в виде контрактов и исключения или уведомления о возникающим, когда они нарушены.</span><span class="sxs-lookup"><span data-stu-id="0e85e-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="0e85e-112">Причины, обуславливающие это то, что множество ошибок выполнен, поскольку объекты находятся в состояние, в котором они никогда не должно было в.</span><span class="sxs-lookup"><span data-stu-id="0e85e-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="0e85e-113">Ниже приведен подробно объясняется из Янг Грег в [дискуссионные](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span><span class="sxs-lookup"><span data-stu-id="0e85e-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="0e85e-114">Давайте предложить, теперь у нас есть SendUserCreationEmailService, принимающий UserProfile... как можно мы рационализации в этой службе, что имя не является null?</span><span class="sxs-lookup"><span data-stu-id="0e85e-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="0e85e-115">Мы устанавливайте его еще раз?</span><span class="sxs-lookup"><span data-stu-id="0e85e-115">Do we check it again?</span></span> <span data-ttu-id="0e85e-116">Или более вероятно... вы просто не использоваться для проверки и «надеемся, что для обеспечения оптимальной» — надеемся, что кто-то утруждать для его проверки перед отправкой его можно.</span><span class="sxs-lookup"><span data-stu-id="0e85e-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="0e85e-117">Конечно с помощью управляемой тестами разработки один первый тестов, которые мы Пишите: Если отправить клиенту с нулевым значением, он должен вызывать ошибку.</span><span class="sxs-lookup"><span data-stu-id="0e85e-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="0e85e-118">Но когда мы начинаем записи этих типов тестов снова и снова помните, мы... «ожидания, если мы никогда не может быть имя, чтобы стать null бы не было все эти тесты»</span><span class="sxs-lookup"><span data-stu-id="0e85e-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="0e85e-119">Реализация проверок в уровне модели домена</span><span class="sxs-lookup"><span data-stu-id="0e85e-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="0e85e-120">Проверки обычно реализуются в конструкторах сущности домена или в методах, которые можно обновлять сущность.</span><span class="sxs-lookup"><span data-stu-id="0e85e-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="0e85e-121">Существует несколько способов реализации проверки, такие как проверка данных и создание исключений, если проверка завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0e85e-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="0e85e-122">Существуют более сложные шаблоны, например с помощью шаблона спецификации для проверки, а также шаблон уведомления для возврата коллекции ошибок вместо возвращения исключения для каждой проверки возникающем совпадении.</span><span class="sxs-lookup"><span data-stu-id="0e85e-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="0e85e-123">Проверка условия и создание исключений</span><span class="sxs-lookup"><span data-stu-id="0e85e-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="0e85e-124">В следующем примере кода показан простой подход к проверке в сущности домена, вызывая исключение.</span><span class="sxs-lookup"><span data-stu-id="0e85e-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="0e85e-125">В таблице ссылок в конце этого раздела можно просмотреть ссылки на более сложные реализации на основе шаблонов, которые мы обсуждали ранее.</span><span class="sxs-lookup"><span data-stu-id="0e85e-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="0e85e-126">Лучше пример продемонстрирует требуется убедиться в внутреннего состояния не был изменен или превышение все гарантированного для метода.</span><span class="sxs-lookup"><span data-stu-id="0e85e-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="0e85e-127">Например следующая реализация объект будет оставаться в недопустимом состоянии:</span><span class="sxs-lookup"><span data-stu-id="0e85e-127">For example, the following implementation would leave the object in an invalid state:</span></span>

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

<span data-ttu-id="0e85e-128">Если недопустимое значение состояния, первая строка адреса и города уже были изменены.</span><span class="sxs-lookup"><span data-stu-id="0e85e-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="0e85e-129">Что может сделать недействительными адрес.</span><span class="sxs-lookup"><span data-stu-id="0e85e-129">That might make the address invalid.</span></span>

<span data-ttu-id="0e85e-130">Аналогичный подход можно использовать в конструкторе сущности, вызывает исключение, чтобы убедиться в том, что сущность является недопустимым после его создания.</span><span class="sxs-lookup"><span data-stu-id="0e85e-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="0e85e-131">С помощью проверки атрибутов в модели, основанной на данных заметок</span><span class="sxs-lookup"><span data-stu-id="0e85e-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="0e85e-132">Другой подход заключается в использовании проверки атрибутов на основании заметок к данным.</span><span class="sxs-lookup"><span data-stu-id="0e85e-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="0e85e-133">Атрибуты проверки предоставляют способ настроить проверку модели, которая по существу аналогично проверки для полей в таблицах базы данных.</span><span class="sxs-lookup"><span data-stu-id="0e85e-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="0e85e-134">Сюда входят ограничения, такие как назначение типов данных или обязательных полей.</span><span class="sxs-lookup"><span data-stu-id="0e85e-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="0e85e-135">Другие виды проверки включают применение шаблонов данных для применения бизнес-правил, таких как номер кредитной карты, номер телефона или адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0e85e-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="0e85e-136">Атрибуты проверки упрощают для применения требований.</span><span class="sxs-lookup"><span data-stu-id="0e85e-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="0e85e-137">Тем не менее как показано в следующем коде, этот подход возможно слишком вмешивается в модели ддд, она примет зависимость ModelState.IsValid из Microsoft.AspNetCore.Mvc.ModelState, который должен вызывать контроллеров MVC.</span><span class="sxs-lookup"><span data-stu-id="0e85e-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="0e85e-138">Проверка модели происходит до каждого вызываемого действия контроллера, и метод контроллера ответственность за проверить результат вызова ModelState.IsValid и реагировать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="0e85e-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="0e85e-139">Решение для его использования зависит от как тесно связаны требуется модель с ИТ-инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="0e85e-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

<span data-ttu-id="0e85e-140">Тем не менее, с точки зрения DDD модель домена лучше всего хранятся бережливого с использованием исключений в методах поведение к сущности, либо путем реализации шаблонов спецификации и уведомления для принудительного выполнения правил проверки.</span><span class="sxs-lookup"><span data-stu-id="0e85e-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="0e85e-141">Проверки платформ, таких как заметок к данным в ASP.NET Core или какие-либо другие проверки платформы, как FluentValidation выполнение требований для вызова платформы приложений.</span><span class="sxs-lookup"><span data-stu-id="0e85e-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="0e85e-142">Например при вызове метода ModelState.IsValid в заметок к данным, необходимо вызвать контроллеры ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0e85e-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="0e85e-143">Имеет смысл использовать заметок к данным на уровне приложения в классах ViewModel (а не сущностями домена), которые будет принимать входные данные для проверки модели на уровне пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0e85e-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="0e85e-144">Тем не менее это должно выполняться не на исключения проверки в модели домена.</span><span class="sxs-lookup"><span data-stu-id="0e85e-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="0e85e-145">Проверка сущностей путем реализации спецификации и шаблонов уведомлений</span><span class="sxs-lookup"><span data-stu-id="0e85e-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="0e85e-146">Наконец более сложный подход к реализации проверки в модели домена — посредством реализации шаблона спецификации в сочетании с шаблон уведомления, как описано в некоторых дополнительных ресурсов, перечислены ниже.</span><span class="sxs-lookup"><span data-stu-id="0e85e-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="0e85e-147">Следует отметить, что может использоваться только один из этих шаблонов — например, проверка вручную с помощью операторов управления, но с помощью шаблона уведомления для стека и возвращают список ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="0e85e-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="0e85e-148">Использование отложенной проверки в домене</span><span class="sxs-lookup"><span data-stu-id="0e85e-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="0e85e-149">Существуют различные подходы для обработки отложенного проверок в домене.</span><span class="sxs-lookup"><span data-stu-id="0e85e-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="0e85e-150">В своей книге [Implementing Domain-Driven разработки](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vernon Вон обсуждается в разделе о проверке.</span><span class="sxs-lookup"><span data-stu-id="0e85e-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="0e85e-151">Двухшаговая проверка</span><span class="sxs-lookup"><span data-stu-id="0e85e-151">Two-step validation</span></span>

<span data-ttu-id="0e85e-152">Также рассмотрите двухшаговой проверки.</span><span class="sxs-lookup"><span data-stu-id="0e85e-152">Also consider two-step validation.</span></span> <span data-ttu-id="0e85e-153">Используйте проверки уровня полей на объекты передачи команды данных (DTO) и проверки на уровне домена внутри сущностей.</span><span class="sxs-lookup"><span data-stu-id="0e85e-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="0e85e-154">Это можно сделать путем возвращения результирующего объекта вместо этого исключения для упрощения работы с ошибками проверки.</span><span class="sxs-lookup"><span data-stu-id="0e85e-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="0e85e-155">Проверка полей с помощью заметок к данным, например, вы не дублируют проверка определение.</span><span class="sxs-lookup"><span data-stu-id="0e85e-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="0e85e-156">Выполнение, однако, может быть серверных и клиентских данных в случае DTO (команды и ViewModels, например).</span><span class="sxs-lookup"><span data-stu-id="0e85e-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e85e-157">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="0e85e-157">Additional resources</span></span>

-   <span data-ttu-id="0e85e-158">**Рэйчел Аппель. Общие сведения о проверке модели в ASP.NET Core MVC**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="0e85e-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="0e85e-159">**Рик Андерсон (Rick Anderson). Добавление проверки**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="0e85e-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="0e85e-160">**Мартин Фоулер (Martin Fowler). Замена создание исключений с уведомлением при проверке**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="0e85e-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="0e85e-161">**Спецификация и шаблоны уведомлений**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="0e85e-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="0e85e-162">**Gorodinski лев. Проверка в разработки на основе домена (DDD)**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="0e85e-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="0e85e-163">**Colin гнездо. Проверка модели домена**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="0e85e-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="0e85e-164">**Джимми Богард (Jimmy Bogard). Проверка данных в мире DDD**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="0e85e-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="0e85e-165">[Предыдущие] (перечисление классы over-enum-types.md) [Далее] (validation.md клиента стороне)</span><span class="sxs-lookup"><span data-stu-id="0e85e-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>
